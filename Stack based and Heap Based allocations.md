**Memory management** defines how a programming language **allocates, uses, and releases RAM** during program execution. It determines efficiency, reliability, and speed.  
At the foundation are two main storage models: the **stack** and the **heap**.

The **stack** provides fast, automatic storage for short-lived variables—ideal for function calls and fixed-size data. The **heap** supports dynamic allocation for objects whose size or lifetime cannot be known at compile time.  
All modern languages combine these two, but their proportions, mechanisms, and automation differ.


## Core Concepts

#### Stack Allocation

- **Definition:** Memory reserved in a contiguous block (the call stack) for each active function call.
- **Management:** Automatic; pushed on function entry, popped on exit.
- **Lifetime:** Bound to the function scope.
- **Structure:** Last-In–First-Out (LIFO).
- **Speed:** Very fast—pointer increment/decrement only.

**Example (C):**

```c
int* p = malloc(sizeof(int)); 
*p = 10; 
free(p);
```

#### Heap Allocation

- **Definition:** Memory dynamically requested at runtime from the OS or runtime allocator.
- **Management:** Manual or automatic (via garbage collector).
- **Lifetime:** Until explicitly freed or collected.
- **Structure:** Unordered; managed through pointers.
- **Speed:** Slower—requires bookkeeping, fragmentation handling, and thread safety.

**Example (C):**

```c
int* p = malloc(sizeof(int));  *p = 10;  free(p);
```

## 2. Why Stack Allocation Is Faster

1. **No fragmentation:** Stack is contiguous and predictable.
2. **Constant-time allocation:** One pointer (`stack pointer`) moves up or down.
3. **Automatic lifetime:** No metadata or reference tracking.
4. **Cache locality:** Stack memory is small and CPU-cache friendly.    

By contrast, **heap allocation**:

- Uses complex data structures (free lists, trees, or arenas).
    
- Requires synchronization across threads.
    
- Must track free/used blocks and sometimes perform compaction.

Hence, Python—where all objects live on the heap—pays this overhead for flexibility.