**Created:** *27.11.25, 03:50*

**Tags:** #CPP #OOP #Constructors

# Constructors in C++

## Definition

- A constructor is a special function that runs automatically when an object is created
- It has the same name as the class and no return type.

`class MyClass { public:     MyClass(); // constructor };`

#### Example: Defining and creating a class using constructor

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

## Key Rules

- same name as the class
- no `return` type
- usually public
- automatically called when the object is created

## Why Constructors Matter

- ensure objects start in a valid state
- enforce in-variants
- implement RAII (acquire resources in constructor, release in destructor)
- allow multiple ways to build an object (overloading)

---
# Types of Constructors

- [[Default Constructor]]
    
- [[Parameterised Constructor]]
    
- [[Copy Constructor]]
    
- [[Delegating Constructor]]
    
- [[Move Constructor]]
    
- [[Converting Constructor]]


## Linked Notes

### **Other Related Concepts**

- [[Constructor Initialization List]]
    
- [[Constructors for const Members]]
    
- [[Constructor Definition Outside Class]]
    
- [[Rule of Three / Orthodox Canonical Form]]
    
- [[Destructor]]
    
- [[Copy Assignment Operator]]


------------
---------
-------

**Status:** 

**Hashtags:**

- #CPP 
- #constructors
- #OOPS 

**Links / Tags:** 
- **Relevance Links:**
	- 

- **Topic Tags:**
	- [[Constructor Overloading in C++]]


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


### Use of Constructors

1. **Automatic initialisation** 
	- Objects are ready to use immediately after creation
    
2. **Encapsulation**
	- Control how objects are set up, enforcing in-variants
    
3. **Overloading**
	- Multiple ways to create objects with different parameters
    
4. **RAII**
	- Acquire resources in constructor, release in destructor
    
5. **Default values**
	- Sensible defaults when no parameters provided



# References


## Closely Related Notes

### Next:

### Prev:

