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
	- 

- **Topic Links:**
	- [[Constructor Overloading in C++]]

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


# Types of Constructors

- [[Default Constructor]]
- [[Parameterised Constructor]]
- [[Copy Constructor]]
- [[Delegating Constructor]]
- [[Move Constructor]]
- [[Converting Constructor]]


---

## Linked Notes:

### Advanced Topics

- [[Constructor Overloading in C++]] - multiple constructors in same class
- [[Constructor Initialisation List]] - How to initialise members efficiently
- [[Constructors for const Members]] - Handling const members in constructors

### Other Related Concepts

- [[Constructor Initialisation List]] - Initialising members efficiently
- [[Constructors for const Members]] - Handling const members in constructors
- [[Constructor Definition Outside Class]] - Defining constructors outside the class
- [[Orthodox Canonical Form in C++]] - Different special member functions and their roles
- Destructors in C++ 
- [[Copy Assignment Operator]]




------------
---------
-------

**Status:** 




# Constructors

## Definition:

- Special Method automatically called when an object of a class is created
- Created using:
	- same name as the class, followed by parentheses `()`;

#### Example:

```cpp
class MyClass
{
public:
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

### Constructor Rules:

- Has same name as the Class
- No return type (not even `void`)
- Usually declared in `public`
- It's automatically called when an object is created

## Constructor with Parameters

- Constructors can also take parameters (just like regular functions)
- useful for setting initial values for attributes

#### Example: constructor with parameters

```cpp
class Car
{
public:
	string brand;
	string model;
	int    year;
	
	Car(string x, string y, int z)
	{
		brand = x;
		model = y;
		year = z;
	}
}

int main()
{
	// Create ar objects and call constructor with  different values
	Car myObj1("BMW", "X5", 1999);
	Car myObj2("Ford", "Mustang", 1969);
	
	// Print values
	cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << endl;
	cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << endl;
	
	return 0;
}
```


## Constructor defined outside the class

- Constructor can also be defined outside the class using **Scope Resolution Operator** `::`

#### Example:

```cpp

class Car          // class  
{
  public:          // Access specifier  
    string brand;  // Attribute 1
    string model;  // Attribute 2
    int year;      // Attribute 3
    Car(string x, string y, int z); // Constructor declaration  
};
  
// Constructor definition outside the class  
Car::Car(string x, string y, int z)
{  
  brand = x;  
  model = y;  
  year  = z;  
} 

int main()
{
  // Create Car objects and call the constructor with different values  
  Car carObj1("BMW", "X5", 1999);  
  Car carObj2("Ford", "Mustang", 1969);  
  
  // Print values  
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";  
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";  
  return 0;  
}

```




# References


## Closely Related Notes

### Next:

### Prev:

