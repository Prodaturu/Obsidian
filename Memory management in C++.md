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