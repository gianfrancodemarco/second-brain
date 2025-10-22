
Python is a high-level, [[dynamically-typed language]] where code blocks are defined by indentation rather than braces. It emphasizes readability (see PEP 8).
Assignment is by reference (names bind to objects), and mutable vs immutable types behave differently under aliasing (e.g. two names can refer to the same list).

![[Pasted image 20251022200153.png]]

> Dictionaries are ordered since python 3.6

### Interpreter

The **Python interpreter** is the core program that executes Python code. It reads source code, converts it into an intermediate representation (bytecode), and runs it line by line in a virtual machine.

_____
The Python interpreter is a **software implementation of the Python language**. It provides:

- **Lexical analysis** and **parsing** of source code.
- **Compilation** into Python bytecode (`.pyc` files).
- **Execution** of bytecode within the **Python Virtual Machine (PVM)**.
- **Runtime environment** for managing objects, memory, and garbage collection.

#### Core Workflow

1. **Source code input** (`.py` file)  
    → UTF-8 text containing Python instructions.
    
2. **Lexical analysis**  
    → Breaks text into tokens (`if`, `x`, `=`, `3`).
    
3. **Parsing**  
    → Builds an Abstract Syntax Tree (AST) from tokens.
    
4. **Compilation**  
    → Converts AST to bytecode (`.pyc`) stored in `__pycache__/`.
    
5. **Execution**  
    → The **PVM** reads bytecode instructions and executes them.

#### PVM

CPython is implemented in **C**, so the PVM loop is essentially **a C function executing bytecode instructions**:

`for (;;) {
    opcode = NEXTOP();
    switch(opcode) {
        case LOAD_CONST:
            push(PyTuple_GET_ITEM(consts, oparg));
            break;
        case BINARY_ADD:
            b = POP();
            a = POP();
            PUSH(PyNumber_Add(a, b));
            break;
        ...
    }
}


Steps:

1. Fetch the next bytecode instruction.
    
2. Decode it into an operation (`opcode`) and optional argument (`oparg`).
    
3. Execute the operation via corresponding C functions (like `PyNumber_Add`).
    
4. Update the stack and program counter.
    

Essentially, the **Python code is indirectly executed** as C code operating on a stack of Python objects.

Python is **interpreted**, not compiled to machine code, though it uses **compilation to bytecode** internally.


#### References

- Python 3 Interpreter and Execution Model — Official Docs
- [CPython Source Code — GitHub](https://github.com/python/cpython)
- PyPy — Official Site
- Python Glossary: Interpreter
- The Python Language Reference
- How Python Runs Programs — Python.org Tutorial
### Memory Management

Python’s memory management system is an automatic and layered mechanism built to balance flexibility with safety. It integrates **reference counting**, **garbage collection**, and **memory pooling** to optimize allocation, reuse, and release of objects in the interpreter.

| Area      | Managed by            | Used for                                             | Lifetime                             |
| --------- | --------------------- | ---------------------------------------------------- | ------------------------------------ |
| **Stack** | C runtime (OS)        | Function call frames, local references, control flow | Automatic, limited to function scope |
| **Heap**  | Python memory manager | All Python objects (lists, ints, dicts, etc.)        | Dynamic, freed via refcount/GC       |

Python code runs inside the **CPython interpreter**, which is implemented in C.  
Each Python function call corresponds to a **C stack frame** that holds:
- A pointer to the current **PyFrameObject** (metadata about the function).
- Local variable references (not the objects themselves).
- Control data for return addresses and exception handling.

All Python objects are **heap-allocated**:
- Integers, strings, classes, modules, functions, closures—all live in heap memory.
- Allocation is handled through **pymalloc** and **the garbage collector**.

This makes Python flexible but slower than [[Stack based and Heap Based allocations|stack-based]] allocation in compiled languages.
### Memory Model Overview

Key components:

- **Object-specific allocators**: each built-in type (e.g., list, dict, set) manages its own internal memory structures.    
- **Object allocator (PyObject_Malloc)**: central layer for small objects.
- **System allocator (malloc/free)**: OS-level memory functions for large allocations.

### Reference Counting

Every Python object maintains a **reference count** (`ob_refcnt`) that tracks how many variables, containers, or temporary expressions refer to it.

**Mechanism:**

- Incremented when a reference is created:

 ```python
    a = [1, 2, 3] 
    b = a  # refcount +1
```

- Decremented when a reference is deleted or reassigned:

  ```python 
   del a  # refcount -1
   ```

When the count reaches **zero**, the memory manager immediately deallocates the object.

**Pros:**

- Deterministic destruction.
- Simple model for small programs.

**Cons:**

- Cannot handle **reference cycles** (objects referencing each other).

### Garbage Collection (Cycle Detection)

To handle cycles (e.g., two objects referencing each other), Python includes a **cyclic garbage collector** (in the `gc` module).  
It complements reference counting by identifying unreachable objects in cycles.

**Implementation details:**

- Uses a **generational approach**, dividing tracked objects into three generations (0, 1, 2).
- Young objects start in generation 0; those surviving multiple collections are promoted.
- Collection is triggered automatically when the number of allocations exceeds a threshold.

**Simplified pseudocode:**

```python
if allocations - deallocations > threshold:
	collect generation 0
```

**Generational hypothesis:**  
Objects that survive early collections are likely to live longer, so older generations are collected less frequently.

**Manual control:**

```python
import gc 
gc.collect() # force collection
gc.disable() # turn off automatic collection 
gc.get_stats()        # view stats per generation
```

### References

1. Python Software Foundation. _Memory Management in Python_. https://docs.python.org/3/c-api/memory.html
2. Python `gc` Module Documentation. https://docs.python.org/3/library/gc.html
3. Python Source Code — _Objects/obmalloc.c_ (CPython implementation of pymalloc)
4. van Rossum, G. (2003). _Unifying types and classes in Python 2.2_. Python Enhancement Proposal (PEP 253).
5. L. Bassi, _Python Internals: Memory Management_, Real Python (2023).
6. P. Sommerlad, _Inside CPython Memory Management_, PyCon Talk (2022).
7. Python Enhancement Proposal 445 — _Add memoryview.cast()_.

## Concurrency
