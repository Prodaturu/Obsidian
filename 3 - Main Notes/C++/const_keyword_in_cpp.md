# Const Keyword in C++

## What const means

`const` tells the compiler that a value cannot be modified after it is created.
It enforces read-only behaviour at compile time.

---

## Where const can appear

### 1. Variables
```
const int x = 5;   // cannot change x
```

### 2. Function parameters
```
void foo(const std::string& s);
```
Protects the argument from accidental modification.

### 3. Pointers and referenced values
```
int* const p;        // pointer is const
const int* p;        // pointee is const
const int* const p;  // both const
```

### 4. References
```
const int& ref = x;  // cannot modify x through ref
```

### 5. Member functions (...() const)
```
int getValue() const;
```
Guarantees the method won’t modify the object.

### 6. Objects
```
const MyClass obj;
```
You may only call const member functions on obj.

---

## Top-level const vs low-level const

### Top-level const
Applies to the object itself:
```
const int a = 10;
```

### Low-level const
Applies to the pointee or referenced value:
```
const int* ptr;      // ptr → low-level const
int* const ptr;      // ptr itself is const (top-level)
```

---

## Why const matters in C++

- prevents accidental modification
- improves API safety
- required for correct overloading (const vs non-const methods)
- affects copy/assignment behaviour
- used heavily in modern C++ and in CPP05 (e.g., const std::string name)

---

## Related Notes
- Const Data Members in C++
- Const Member Functions in C++
- Const-Correct Getters in C++
- Const Objects and Member Function Calls in C++
- Const and Copy / Assignment Semantics in C++
- Pointer and Reference Types in C++