**Created:** 07.12.25, 01:18

**Status:** #map  

**Hashtags:**
- #cpp
- #language_features
- #memory_management
- #overview

**Links / Tags:**
- **Parent Map:**
  - C++ Language Features

- **Related Notes:**
  - [[Stack vs Heap (C++)]]
  - [[Dynamic Memory Allocation in C++ (new / delete)]]
  - [[RAII and Smart Pointers in C++]]
  - [[C++ Error Handling]]
  - [[C++ Data Types]]

# Memory Management in C++

How C++ creates, stores, and destroys objects in memory.

- Main axes:
  - **Where** memory lives (stack, heap, static storage).
  - **How long** it lives (storage duration / lifetime).
  - **Who** owns it (ownership).
  - **Who** frees it (you vs RAII vs library).

---
## 1. Memory regions: Stack, Heap, Static

### 1.1 Stack

- Automatic Storage
- It is used for
	- Function parameters
	- Local variables with *automatic* storage duration

#### Properties of Stack

- Allocated and freed automatically when a function is called / returns



### 1.1 Stack (Automatic storage)

- Used for:
  - Function parameters.
  - Local variables with *automatic* storage duration.
- Properties:
  - Allocated and freed automatically when a function is called / returns.
  - Very fast, contiguous.
  - Limited in size.
- C++ view:
  - Variables like:
    ```cpp
    void f() {
        int x = 10;      // automatic (stack)
        std::string s;   // s is on stack, but it may use heap internally
    }
    ```
  - Lifetime: from the point of declaration until the end of the block.

### 1.2 Heap / Free store (Dynamic storage)

- Used for:
  - Objects whose lifetime you control manually or via smart pointers.
- Properties:
  - Allocated explicitly.
  - Freed explicitly (or by RAII / smart pointer).
  - More flexible, but slower and more error-prone.
- C++ view:
  - Using `new` / `delete` or smart pointers (recommended):
    ```cpp
    int* p = new int(5);     // allocate on heap
    delete p;                // free
    ```

### 1.3 Static / Global storage

- Used for:
  - `static` variables, global variables, namespace-scope variables.
- Lifetime:
  - From program start to program end (with some details for initialization order).
- C++ example:

```cpp

int global = 0;       // static storage duration

void f()
{
	static int x = 0; // also static storage duration
}
```

## 2. Storage duration and lifetime in C++

C++ has formal categories:

- **Automatic**: local variables without `static`.
- **Static**: globals, `static` locals, `constexpr` at namespace scope.
- **Dynamic**: allocated with `new`, `new[]`, `malloc`, etc.
- **Thread-local**: `thread_local` variables, one per thread.

Key idea:

> Lifetime = period where it is legal to use the object through any pointer/reference to it.

---

## 3. Dynamic memory in C++ (Heap)

See: [[Dynamic Memory Allocation in C++ (new / delete)]] for details.

### 3.1 `new` and `delete`

- **Single object**:
    
    `int* p = new int(42); delete p;`
    
- **Arrays**:
    
    `int* arr = new int[10]; delete[] arr;`
    
- Problems if misused:
    
    - Memory leaks (forgetting `delete`).
        
    - Double `delete`.
        
    - `delete` vs `delete[]` mismatch.
        
    - Dangling pointers (use after free).
        

### 3.2 `malloc` / `free` (C-style)

- From `<cstdlib>`.
- Do **not** call constructors / destructors.
- Should not be mixed with `new` / `delete`.

In modern C++, prefer:

- `new` / `delete` only when you really need it.
- Even better: **avoid raw `new` / `delete`** in application code; use RAII and smart pointers.

---

## 4. RAII and Smart Pointers

See: [[RAII and Smart Pointers in C++]].

### 4.1 RAII (Resource Acquisition Is Initialisation)

- Idea:
    
    - Resource is acquired in a constructor.
    - Released in the destructor.

#### Example:
```cpp
struct File {
    FILE* f;
    File(const char* path) : f(std::fopen(path, "r")) {}
    ~File() { if (f) std::fclose(f); }
};

void g() {
    File file("data.txt"); // opened here
    // use file
} // file automatically closed here

```

RAII works with:

- Memory
- Files
- Locks (mutexes)
- Network sockets, etc.


### 4.2 Smart pointers

- **`std::unique_ptr<T>`**
    
    - Exclusive ownership.
    - Cannot be copied (only moved).
    - Best default when you need dynamic allocation.
    
- **`std::shared_ptr<T>`**
    
    - Shared ownership, reference counting.
    - Extra overhead; use only when you need shared ownership.
      
- **`std::weak_ptr<T>`**
    
    - Non-owning reference that can observe a `shared_ptr` without extending its lifetime.


Prefer using factory helpers:

```cpp
auto p = std::make_unique<Foo>(args...);
auto sp = std::make_shared<Foo>(args...);
```

## 5. Ownership and value semantics

C++ encourages **value semantics**:

- Prefer: