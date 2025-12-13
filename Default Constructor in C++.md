**Created:** <span class ="color-green">13.12.25, 15:05</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #cpp
	- #constructors
	- #atomic
- **Topic Tags:**
	- #defaultconstructor
	- #initialization
	- #objectcreation

**Links / Tags:** 
- **Relevance Links:**
	- Types of Constructors in C++        <!-- parent -->
- **Topic Links:**
	- 

---

# Default Constructor in C++

a **default constructor** is a constructor that can be called **with no arguments**.

it is used when an object is created without providing any parameters.

---

## what counts as a default constructor

### implicit default constructor

if you do **not** define any constructor, the compiler may generate one:

```cpp
class A
{
    int x;
};

A a;   // default constructor is implicitly generated
```

- The `A a` calls the defaults constructor is implicitly called
- This constructor:
	- Does not initialise fundamental types
	- Value Initialises members only in some contexts

### User-defined default constructor
```cpp
class A
{
public:
	A()
	{
	// custom setup
	// we can write something we want to do here
	// where as the default just initalizes the class
	}
};
```

- Now the compiler will not generate its own default constructor

### Default Constructor and member Initialisation

```cpp

```
