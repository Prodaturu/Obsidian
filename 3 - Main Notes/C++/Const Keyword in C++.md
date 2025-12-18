**Created:** 10.12.25, 14:46*

**Note Type:** #atomic

**Hashtags:**

- **Relevance Tags:**
    - #cpp 
    - #cvqualifiers
- **Topic Tags:**
    - #const
    - #immutability

**Links / Tags:**

- **Relevance Links:**
    - Const in C++
- **Topic Links:**
    - [[Const Placement Rules in C++]]
    - [[Const Member Functions in C++]]
    - [[Const Objects in C++]]
    - [[Pointer and Reference Types in C++]]

---

# Const Keyword in C++
- `const` tells the compiler that something **cannot be modified** after it is initialised
- it enforces **read-only guarantees** at compile time

---

## Where `const` can appear

### Variables

```cpp
const int x = 9;
```
- `x` cannot be reassigned after initialisation

---

### Function parameters

```cpp
void foo(const std::string& s);
```

- protects the argument from accidental modification

---

### Pointers and pointed values

```cpp
int* const p;        // pointer is const
const int* p;        // pointed value is const
const int* const p;  // both are const
```

- exact meaning depends on placement
- detailed rules live in:
    - Const Placement Rules in C++

---

### References

```cpp
const int& ref = x;
```

- value cannot be modified through the reference

---

### Member functions

```cpp
int getValue() const;
```

- guarantees the function does not modify the object

see:
- Const Member Functions in C++

---

### Objects

```cpp
const MyClass obj;
```

- only `const` member functions may be called

see:
- Const Objects in C++

---

## Key idea

`const` always applies to **something specific**.

understanding `const` means understanding **what is being protected from change**.

---

# Internal References

# External References