**Created:** *<span class ="color-green">09.12.25, 08:12</span>*

**Note Type:** #atomic 

**Hashtags:**

- **Relevance Tags:**
    - #cpp
    - #OOPS 
    - #classdesign
    - #specialmemberfunctions
    
- **Topic Tags:**
    - #copyassignmentoperator
    - #assignmentoperator
    - #operatoroverloading 
    - #copy

**Links / Tags:**

- **Relevance Links:**
    - Classes and Objects in C++ <!-- main parent, plain text -->
    - Canonical Forms in C++ <!-- lifetime cluster, plain text -->
    - Operator Overloading in C++
    - Classic Canonical Form in C++
    - Rules of Three Five and Zero in C++
      
- **Topic Links:**
	- [[Default Copy Assignment in C++]]
	- [[Overloading Copy Assignment Operator in C++]]


---

# Copy Assignment Operator in C++

> Assigns one existing object’s contents to another existing object of the same class.

- It is both:
	- a **special member function** (controls object lifetime)
	- an **overloaded operator** (`operator=`)

## Kinds of Copy Assignment Operators

- [[Default Copy Assignment in C++|Default Copy Assignment Operator]]
	- Generated automatically by compiler
	- When we don't write our own
	  
- [[Overloading Copy Assignment Operator in C++|Overloaded Copy Assignment Operator]]
	- [[Overloading Copy Assignment Operator in C++|User Defined Copy Assignment Operator]]
	- Replaces or extends the default behaviour

## Typical signature

```cpp
Myclass& operator=(const MyClass& other);
```

- `MyClass&`
	- `return`s a reference to `*this` so we can chain assignments ( a = b = c;)
	  
- `const MyClass& other`
	- 

# Internal References



# External References
