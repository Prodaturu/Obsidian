**Created:** 27.11.25, 20:50

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Virtual Functions in C++

- Functions that enable **Runtime Polymorphism** 
	- Done by allowing the correct function to be called based on the actual object type at runtime

## Core Mechanism

```cpp
class Base
{
public:
	virtual void show()
	{cout << "Base show" << endl;}
};

// class `Derived`, that's "Derived" from the `Base` "Parent" Class
class Derived : public Base
{
public:
	void show() override
	{
		cout << "Derived show" << endl;
	}
};

// How it works: //
int main()
{
	Base* baseObjPtr;
	Derived derivedObj;
	
	baseObjPtr = &derivedObj;
	basePtr->show(); //calls Derived::show() aT RUNTIME -> (compile-time decision)
	// without virtual: 
		// It would call Base::show()
}
```

## Key Syntax Elements

### Virtual Declaration

`virtual returnType functionName(parameters);`

### Override Specification

`returnType functionName(parameters) override;`

### Complete Example

```cpp
#include <iostream>
using namespace std;

class Animal
{
public:
	virtual void speak()
	{
		cout << "some animal sounds" << endl;
	}
};

class Dog : public Animal {
public:
    void speak() override {  // Overrides base function
        cout << "Woof! Woof!" << endl;
    }
};

class Cat : public Animal {
public:
    void speak() override {  // Overrides base function
        cout << "Meow!" << endl;
    }
};

int main()
{
	Animal* animal;
	
	Dog dog;
	Cat cat;
	
	animal = &dog;
	animal->speak(); // Output: "Woof! Woof!" (Runtime decision)
	
	animal = &cat;
	animal->speak() // Output: "Meow!" (Runtime decision)
	
	// without virtual keyword, both would output: "some animal sound"
}
```

### Virtual Destructors

```cpp
class Base {
public:
    virtual ~Base() {  // Virtual destructor
        cout << "Base destroyed" << endl;
    }
};

class Derived : public Base {
public:
    ~Derived() override {
        cout << "Derived destroyed" << endl;
    }
};

// Usage:
Base* ptr = new Derived();
delete ptr;  // Calls both Derived THEN Base destructor
// Without virtual destructor: Would only call Base destructor
```


### Rules and Behaviour

- **Runtime Decision**
	- Function called depends on actual object type
	- not pointer type
	  
- **Override Keyword**
	- Ensures you are actually overriding a virtual function
	
- **Virtual Destructors**
	- Essential when deleting through base pointers
	
- **Can Have Implementation**
	- Virtual functions can have default implementations

### Without Virtual (Static Binding)

```cpp
Base* ptr = new Derived();
ptr->show();  // Calls Base::show() always
```

### With Virtual (Dynamic Binding)

```cpp
Base* ptr = new Derived();
ptr->show();  // Calls Derived::show() - checks actual object type
```

# References


## Closely Related Notes

### Next:

### Prev:
