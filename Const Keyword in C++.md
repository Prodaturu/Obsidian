a **Created:** *<span class ="color-green">10.12.25, 14:46</span>*

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
	- #cpp 
	- #cvqualifiers 
- **Topic Tags:**
	- #const 
	- 

**Links / Tags:** 
- **Relevance Links:**
	- CV-Qualifiers in C++
- **Topic Links:**
	- [[Pointer and Reference Types in C++]]

---
# Const Keyword in C++

- `const` tells compiler that a value **cannot be modified** after creation
- enforces **read-only** behaviour at compile time

## Where 'const' can appear

### Variables

```cpp
const int x = 9; //cannot change x;
```

### Function Parameters

```cpp
void foo(const std::string& s);
```

- Protects the argument from accidental modification

### Pointers and referenced values

```cpp
int* const p // pointer is const
const int* p // pointee is const
const int* const p // both const
```

### **References**

```cppconst int& ref = x;  // cannot modify x through ref```

### 5. **Member functions (`...() const`)**

`int getValue() const;`

Guarantees the method won’t modify the object.

### 6. **Objects**

`const MyClass obj;`

You may only call `const` member functions on `obj`.

# Internal References


# External References
