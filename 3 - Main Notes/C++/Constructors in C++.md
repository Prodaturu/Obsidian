**Created:** *27.11.25, 03:50*

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
	- #CPP , #OOP , #constructors , #map 
- **Topic Tags:**
	- #specialmemberfunctions    
	- #raii    
	- #classdesign

**Links / Tags:** 
- **Relevance Links:**
	- [[Types of Constructors in C++]]  

- **Topic Links:**
	- [[Advanced Constructor Concepts in C++]] 
	- Destructors in C++ 
	- Copy Assignment Operator


# Constructors in C++

## Definition

- A constructor is a special function that runs automatically when an object is created
- It has the same name as the class and no return type.

```cpp
class MyClass
{
public:
	MyClass(); // constructor 
};
```

#### Example: Defining and creating a class using constructor

```cpp
class MyClass
{
public:
	// A public Constructor to create the class
	MyClass()
	{
		cout << "Hello World!";
	}
}

int main()
{
	MyClass myObj; // will call the constructor
	return 0;
}
```

## Key Rules

- Constructor must have **same name** as the class
- no `return` type
- usually `public`
- automatically called when the object is created

## Why Constructors Matter

- **Automatic initialisation**  
  Objects start in a valid state immediately after creation.

- **[[Encapsulation in C++|Encapsulation]] and invariants**  
  The constructor controls how the object is set up and can enforce invariants.

- **RAII (Resource Acquisition Is Initialisation)**  
  Acquire resources in the constructor, release them in the destructor.

- **[[Constructor Overloading in C++|Overloading]]**  
  Provide multiple ways to create an object with different parameter sets.

- **Default values**  
  Allow creating objects with sensible defaults when no arguments are given.

# Related Notes

## Sub-maps

- [[Types of Constructors in C++]] 
	- Default, parameterised, copy, Delegating, Move, Converting
    
- [[Advanced Constructor Concepts in C++]]  
	- Constructor Overloading
	- 
	- [[Constructor Overloading in C++]] - multiple constructors in same class
	- [[Constructor Initialisation List]] - How to initialise members efficiently
	- [[Constructors for const Members]] - Handling const members in constructors
	- [[Constructor Definition Outside Class]] - Defining constructors outside the class
	- [[Orthodox Canonical Form in C++]] - Different special member functions and their roles
	  
- Other Related Notes:
	- Destructors in C++ 
	- Copy Assignment Operator

# Types of Constructors




---

## Linked Notes:

### Advanced Topics


### Other Related Concepts


# References
