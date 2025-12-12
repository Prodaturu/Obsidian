---
aliases:
  - OCF in C++
  - OCF C++
  - Orthodox Canonical Form
  - OCF
  - Classic Canonical Form in C++
---
**Created:** 08.12.25, 05:30

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
	- 
- **Topic Tags:**
	- 

- **Links / Tags:** 
	- **Relevance Links:**
	- Canonical Forms in C++
	- Classes and Objects in C++
- **Topic Links:**
	- 

---

# Orthodox Canonical Form in C++

- Orthodox Canonical Form (OCF) is a **classic C++98 idiom**:
	
- Used to make a class’s lifetime behaviour **explicit, predictable, and safe**
	
- A class explicitly declares:
	- [[Default constructor]] 
	- [[Copy constructor]]
	- [[Copy Assignment Operator in C++ | Copy Assignment Operator]]
	- [[Destructors in C++|Destructor]]
	
- so its **lifetime behaviour is fully defined and visible**
	
- In C++11 and later, a “modern” canonical form may also add:
	- move constructor
	- move assignment operator
	
- but the core idea stays the same:
- **the class clearly controls how it is created, copied, moved, and destroyed.**

---
## Classic canonical form (C++98 style)

```cpp
class Buffer
{
private:
    int* data;
    size_t size;
    
public:
    Buffer();                              // default constructor
    Buffer(const Buffer& other);           // copy constructor
    Buffer& operator=(const Buffer& other); // copy assignment
    ~Buffer();                             // destructor
};
``` 

- This is called *orthodox* because it follows the traditional, explicit C++98 object model

## What problem Orthodox Canonical Form solves

- Without OCF:
	- The compiler may generate copy and assignment behaviour automatically
	- That behaviour may be incorrect for classes that own resources
	- ownership rules are hidden and unclear
	
- With OCF:
	- Copy behaviour is intentional
	- assignment behaviour is intentional
	- destruction behaviour is visible
	- object lifetime is easy to reason about

## Responsibility of each function for OCF

#### Default Constructor

- Defines how a valid object is created with no arguments
- Ensures the object starts in a usable state

#### Copy Constructor

- Defines how a **new object** is created from an existing object
- called when:

```cpp
T b(a);
T b = a; // b is just created
```

#### Copy Assignment Operator

- Defines how an **existing object** is overwritten by another object
- Called when:
```cpp
b = a; // b was created well before assignment
```

#### Destructor
- Defines 

# Internal References

# External References
