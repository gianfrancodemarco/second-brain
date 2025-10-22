
Python is a high-level, dynamically-typed language where code blocks are defined by indentation rather than braces. It emphasizes readability (see PEP 8).
Assignment is by reference (names bind to objects), and mutable vs immutable types behave differently under aliasing (e.g. two names can refer to the same list).

![[Pasted image 20251022200153.png]]

> Dictionaries are ordered since python 3.6

## Memory Management

Python’s memory management system is an automatic and layered mechanism built to balance flexibility with safety. It integrates **reference counting**, **garbage collection**, and **memory pooling** to optimize allocation, reuse, and release of objects in the interpreter.

### Memory Model Overview

Key components:

- **Object-specific allocators**: each built-in type (e.g., list, dict, set) manages its own internal memory structures.    
- **Object allocator (PyObject_Malloc)**: central layer for small objects.
- **System allocator (malloc/free)**: OS-level memory functions for large allocations.

### Reference Counting

Every Python object maintains a **reference count** (`ob_refcnt`) that tracks how many variables, containers, or temporary expressions refer to it.

**Mechanism:**

- Incremented when a reference is created:
    
    `a = [1, 2, 3] b = a  # refcount +1`
    
- Decremented when a reference is deleted or reassigned:
    
    `del a  # refcount -1`
    

When the count reaches **zero**, the memory manager immediately deallocates the object.

**Pros:**

- Deterministic destruction.
    
- Simple model for small programs.
    

**Cons:**

- Cannot handle **reference cycles** (objects referencing each other).
## GIL
