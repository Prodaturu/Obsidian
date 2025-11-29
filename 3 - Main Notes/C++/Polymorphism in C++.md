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

## Types of Polymorphism

### 1. Compile-time Polymorphism

- These are **Resolved during Compilation**

- **Function Overloading**
	- Same function name, different parameters

```cpp
void print(int a){};
void print(double a){};
void print(string a){};
```

- **Operator Overloading**
	- Redefining operators for user-defined types
```cpp
class Vector
{
	Vector operator+(vector other) {};
}
```

- **Constructor Overloading**
	- Multiple constructors with different parameters

### 2. Runtime Polymorphism (Dynamic / Late Binding)

- Resolved during **Runtime**

- **Virtual Function Mechanism:**
```cpp
#include <iostream>
using namespace std;

class Animal
{
public:
    // VIRTUAL - enables runtime binding
    virtual void speak() {cout << "Animal speaks" << endl;}
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
```

# References

## Closely Related Notes

### Next:

### Prev:
