**Created:** *<span class ="color-green">10.12.25, 02:33</span>*

**Note Type:** #atomic 

**Hashtags:**
- **Relevance Tags:**
	- #cpp 
	- #OOPS 
	- #classdesign 
- **Topic Tags:**
	- #copyconstructor
	- #copysemantics 
	- #specialmemberfunctions 

**Links / Tags:** 
- **Relevance Links:**
	- Classes and Objects in C++ %% Parent %%
	- Canonical Forms in C++ %% Lifetime cluster %%
	- Copy Semantics %% Shallow vs Deep %%
- **Topic Links:**
	- [[Shallow Copy in C++]]
	- [[Deep copy in C++]]
	- [[Copy Assignment Operator in C++]]
	- [[Rules of Three Five and Zero in C++]]


---

# Copy Constructor in C++

> Special Constructor used to create a new Object from an existing object of same class

- A **Special Member Function**
- Controls how an Object is *copied at creation time*

## Basic Syntax

```cpp
class MyClass
{
public:
	MyClass(const MyClass &other);
}
```

**Parts:**
- `MyClass`
	- name of the class
	- constructor must have the **same name** as the class
- `const MyClass &other`
	- source object we are copying from
	- `const` $\rightarrow$ we promise not to modify `other`
	- reference `&` $\rightarrow$ no extra copy just for the parameter

## When is the copy constructor called?

#### Typical Cases:

```cpp
MyClass a; // existing object

MyClass b(a);  // 1) direct copy initialization
MyClass c = a; // 2) copy initialization

void func(MyClass x);
func(a);       // 3) pass by value → copy

MyClass make();
MyClass d = make(); // 4) return by value (may call copy constructor(ctor), or elide / move)
```

- Copy Constructor $\rightarrow$ Creating new from existing
- Copy Assignment $\rightarrow$ Replace existing from existing

see: [[Copy Assignment Operator in C++]]



# Internal References



# External References
