**Created:** 07.12.25, 01:18

**Status:** #notes

**Hashtags:**

- #cpp
    
- #memory_management
    
- #language_features
    
- #systems_programming
    

---

## What is Memory Management in C++?

Memory management is how C++ allocates, uses, and releases memory during program execution.  
C++ gives **manual control**, unlike garbage-collected languages.

This makes C++ fast and flexible, but error-prone if misused.

---

## Memory Areas in C++

### 1. Stack

- Stores local variables and function calls
- Automatic allocation and deallocation
- Very fast
- Limited size

`void func() {     int x = 10;   // stack }`

---

### 2. Heap

- Used for dynamic memory allocation
- Manual allocation and deallocation
- Slower than stack
- Large memory area

`int* p = new int(10);   // heap delete p;`

---
### 3. Static / Global Memory

- Global variables
- `static` variables
- Exists for entire program lifetime

`static int count = 0;`

---
## Storage Duration Types

|Type|Lifetime|
|---|---|
|Automatic|Function scope|
|Static|Entire program|
|Dynamic|Until manually freed|

---
## Dynamic Memory Allocation

- Used when:
	
	- Size is not known at compile time
	- Lifetime exceeds function scope

### `new` and `delete`

`int* p = new int;      // allocate delete p;             // deallocate`

### With initialization

`int* p = new int(5); delete p;`

---

### Arrays: `new[]` and `delete[]`

`int* arr = new int[5]; delete[] arr;`

⚠ Important:

- `new` → `delete`
- `new[]` → `delete[]`

---

## Common Memory Errors

### Memory Leak

Memory allocated but never freed.

`int* p = new int(10); // no delete`

---

### Dangling Pointer

Pointer pointing to freed memory.

`int* p = new int(5); delete p; // p is dangling`

---

### Double Delete

Deleting the same memory twice.

`delete p; delete p;   // error`

---

## Null and Smart Handling

### Best practice after delete

`delete p; p = nullptr;`

---

## RAII (Resource Acquisition Is Initialization)

- Resource tied to object lifetime
    
- Used widely in C++
    
- Prevents memory leaks
    

`class MyClass {     int* data; public:     MyClass() {         data = new int(10);     }     ~MyClass() {         delete data;     } };`

Destructor ensures cleanup.

---

## Smart Pointers

Introduced to avoid manual memory management.

Located in `<memory>`.

---

### `std::unique_ptr`

- Single owner
    
- Cannot be copied
    

`#include <memory>  std::unique_ptr<int> p = std::make_unique<int>(10);`

---

### `std::shared_ptr`

- Multiple owners
    
- Reference counting
    

`std::shared_ptr<int> p1 = std::make_shared<int>(20); std::shared_ptr<int> p2 = p1;`

Memory freed when last owner dies.

---

### `std::weak_ptr`

- Non-owning reference to `shared_ptr`
    
- Prevents circular references
    

`std::weak_ptr<int> wp = p1;`

---

## malloc/free vs new/delete

|malloc/free|new/delete|
|---|---|
|C-style|C++-style|
|No constructor call|Calls constructor|
|No type safety|Type safe|
|Returns `void*`|Returns typed pointer|

Use `new/delete` in C++.

---

## Best Practices

- Prefer stack memory when possible
    
- Avoid raw `new` and `delete`
    
- Use smart pointers
    
- Follow RAII
    
- Always match allocation/deallocation
    
- Set pointers to `nullptr` after delete
    

---

## Cross-Links

- [[Dynamic Memory Allocation in C++]]
    
- [[Pointers in C++]]
    
- [[OOPS in C++]]
    
- [[C++ Smart Pointers]]