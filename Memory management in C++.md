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

cat /etc/passwd

# Memory Management in C++

How C++ creates, stores, and destroys objects in memory.

- Main axes:
  - **Where** memory lives (stack, heap, static storage).
  - **How long** it lives (storage duration / lifetime).
  - **Who** owns it (ownership).
  - **Who** frees it (you vs RAII vs library).

---
## 1. Memory regions: Stack, Heap, Static

### 1.1 Stack (in C++)

- Automatic Storage
- It is used for
	- Function parameters
	- Local variables with *automatic* storage duration

#### Properties of Stack

- Allocated and freed automatically when a function is called / returns
- Very fast, contiguous.
- Limited in size.
 ```cpp
void f()
{
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

### 3.1 'new' and 'delete'

- **Single object**:
    `int* p = new int(42); delete p;`
    
- **Arrays**:
    `int* arr = new int[10]; delete[] arr;`
    
- Problems if misused:
    
    - Memory leaks (forgetting `delete`).
    - Double `delete`.
    - `delete` vs `delete[]` mismatch.
    - Dangling pointers (use after free).

### 3.2 'malloc' / 'free' (C-style)

- From `<cstdlib>`.
- Do **not** call constructors / destructors.
- Should not be mixed with `new` / `delete`.

In modern C++, prefer:

- `new` / `delete` only when you really need it.
- Even better: **avoid raw `new` / `delete`** in application code;
	- use RAII and smart pointers.

---
## 4. RAII and Smart Pointers

See: [[RAII and Smart Pointers in C++]].

### 4.1 RAII (Resource Acquisition Is Initialisation)

- Idea:
    
    - Resource is acquired in a constructor.
    - Released in the destructor.

#### Example:
```cpp
struct File
{
    FILE* f;
    File(const char* path) : f(std::fopen(path, "r")) {}
    ~File() { if (f) std::fclose(f); }
};

void g()
{
    File file("data.txt"); // opened here
    // use file
}   // file automatically closed here

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

C++ encourages **value semantics** over raw pointers:

- Prefer:
```cpp
std::string s = "hello";          // value
std::vector<int> v = {1, 2, 3};  // value
```

Ownership rules:

- If you use raw pointers:
    
    - Clearly decide who _owns_ the object.
    - Document whether the pointer is owning or non-owning.
    
- References (`T&`, `const T&`):
    
    - Never own.
    - Just aliases.

Patterns:

- **Rule of 3/5/0**:
    
    - If you manage a resource manually, you may need custom destructor, copy/move constructors, and assignment operators.
    - If you use RAII types (like `std::string`, `std::vector`, smart pointers), you often need none (Rule of 0).

---
## 6. Common memory errors in C++

- **Memory leak**:
	- You allocate memory and never free it.

- **Dangling pointer / reference**:
```cpp
int* p;
{     
	int x = 10;
	p = &x;  // p points to x
}            // x is destroyed, but p is now dangling
```

- **Use-after-free**:
```cpp
int* p = new int(5);
delete p;

*p = 10;  // undefined behavior
```

- **Double delete**:
```cpp
int* p = new int(5);
delete p;
delete p; // undefined behavior
```

- **Incorrect array delete**:

```cpp
int* a = new int[10];
delete a;    // wrong delete[] a;  // correct
```
 
---
## 7. Best practices (cheat sheet)

- Prefer **stack** objects and **value types** whenever possible.
- When you need dynamic allocation:
    
    - Prefer **`std::unique_ptr` / `std::shared_ptr`** over raw `new` / `delete`.
    - Use `std::make_unique` / `std::make_shared`.
    
- Avoid manual `new` / `delete` in high-level code.
- Use RAII for any resource that needs cleanup.
- Keep ownership clear:
    
    - Who creates?
    - Who destroys?
    
- Turn on warnings and use tools (sanitizers, valgrind, etc.) to catch bugs.

---

## 8. Links to deeper notes

- [[Stack vs Heap (C++)]] – detail how C++ uses stack/heap in practice.
    
- [[Dynamic Memory Allocation in C++ (new / delete)]] – syntax, patterns, and pitfalls.
    
- [[RAII and Smart Pointers in C++]] – patterns for safe memory management.
    
- [[C++ Error Handling]] – interactions between exceptions and resource management (RAII).


``If you want, next step I can write the child notes:  - `Stack vs Heap (C++)` - `Dynamic Memory Allocation in C++ (new / delete)` - `RAII and Smart Pointers in C++`  in the same style.``