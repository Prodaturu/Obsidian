**Created:** *<span class ="color-green">09.12.25, 23:58</span>*

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
	- 
- **Topic Tags:**
	- 

**Links / Tags:** 
- **Relevance Links:**
	- 
- **Topic Links:**
	- 

---

# Types of Polymorphism in C++

## 1. Compile-time Polymorphism

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

## 2. Runtime Polymorphism (Dynamic / Late Binding)

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


# External References
