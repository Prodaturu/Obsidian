**Created:** 27.11.25, 16:50

**Status:** 

**Hashtags:**
- #OOPS 
- #CPP 
- #polymorphism 
- #compiletimepolymorphism 
- #runtimepolymorphism 
- #functionoverloading 
- #operatoroverloading 
- #virtualfunctions

**Links / Tags:** 
- **Relevance Links:**
	- OOPS in C++

- **Topic Tags:**
	- [[Function Overloading in C++]]
	- [[Operator Overloading in C++]]
	- [[Virtual Functions in C++]]
	- [[Abstract Classes in C++]]
	- [[Templates in C++]]


# Polymorphism

- Polymorphism $\implies$ "Many forms"
- Ability to process objects differently based on their data type or class
- Same Interface, different Implementations

## Types of Polymorphism

### 1. Compile-time Polymorphism

- These are **Resolved during Compilation**

#### Function Overloading

- Same function name, different parameters
```cpp
void print(int a){};
void print(double a){};
void print(string a){};
```

#### Operator Overloading

- Redefining operators for user-defined types
```cpp
class Vector
{
	Vector operator+(vector other) {};
}
```

#### Constructor Overloading

- Multiple constructors with different parameters
```cpp
class Rectangle
{
private:
	int width, height;
public:
	Rectangle(){width = height = 0;}                 // Default
	Rectangle(int w, int h) {width = w; height = h;} // Parameterized
	Rectangle(int size) {width = height = size;}     // Square
};
```

### 2. Runtime Polymorphism (Dynamic / Late Binding)

- Resolved during **Runtime** / **Program Execution**

#### Virtual Function Mechanism

```cpp
#include <iostream>
using namespace std;

class Animal
{
public:
    // VIRTUAL - enables runtime binding
    virtual void speak() {cout << "Animal speaks" << endl;}
    
    virtual ~Animal() = default;
};

class Dog : public Animal
{
public:
	// OVERRIDE - replaces parent's implementation
	void speak() override {cout << "Woof! Woof!" << endl;}
};

class Cat : public Animal
{
public:
	void speak() override {cout << "Meow!" << endl;}
};

// Usage demonstrating runtime decision:
int main()
{
	Animal* animal;
	
	Dog dog;
	Cat cat;
	
	animal = &dog;
	animal->speak(); /* Output: "Woof! Woof!" (Runtime decision)*/
	
	animal = &cat;
	animal->speak(); /* Output: "Meow!" (Runtime decision)*/
	
	//without 'virtual' -> Both would ouput: "Animal speaks"
}
```

### 3. Key Differences

| Aspect   $\Downarrow$ | Compile-time    $\Downarrow$               | Runtime    $\Downarrow$ |
| --------------------- | ------------------------------------------ | ----------------------- |
| **Resolution**        | During compilation                         | During execution        |
| **Performance**       | Faster                                     | Slightly slower         |
| **Flexibility**       | Limited                                    | High                    |
| **Mechanism**         | Function overloading, Operator overloading | Virtual functions       |

### When to use Which?

- **Compile-time**
	- When behaviour is known at compile time
- **Runtime**
	- When behaviour depends on actual object type at runtime

### Mental Models

- **Compile-time**
	- The compiler decides which function to call
- **Runtime**
	- The program checks the actual object at runtime

# References

## Closely Related Notes

### Next:

### Prev:
