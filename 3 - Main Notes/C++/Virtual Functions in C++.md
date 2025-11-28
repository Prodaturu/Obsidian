**Created:** 27.11.25, 20:50

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**
	- [[Abstract Classes in C++]]

# Virtual Functions in C++

- **Definition**:
	- Member functions that can be overridden in derived classes to enable runtime polymorphism.
- **Purpose**:
	- Ensure the correct function is called based on the **actual object type** at runtime, not the pointer type.


## 🎯 Core Problem Solved

### Without Virtual (Static Binding)

```cpp

Base* ptr = new Derived();
ptr->show(); // Always calls Base::show() - WRONG!
```

### With Virtual (Dynamic Binding)

```cpp

Base* ptr = new Derived();
ptr->show(); // Calls Derived::show() - CORRECT!
```

## ⚡ Quick Syntax

### Declaration

- `virtual returnType functionName(parameters);`

### Override

- `returnType functionName(parameters) override;`

## 🚀 Essential Example

```cpp

class Animal {
public:
    virtual void speak() { cout << "Animal sound"; }
};

class Dog : public Animal {
public:
    void speak() override { cout << "Woof!"; } // Override
};

// Usage:
Animal* animal = new Dog();
animal->speak(); // "Woof!" (Runtime decision)
```

## 🔑 Key Rules

- **`virtual`** in base class
- **`override`** in derived class (optional but recommended)
- **Runtime decision** - based on object type, not pointer type
- **Virtual destructors** needed when deleting through base pointers

## 💀 Virtual Destructors

- **ALWAYS use virtual destructors in base classes:**

```cpp
class Base
{
public:
    virtual ~Base() {} // ← Essential!
};

Base* ptr = new Derived();
delete ptr; // Calls both Derived::~Derived() AND Base::~Base()
```

## 📋 Cheat Sheet

|Situation|Result|
|---|---|
|`Base* ptr = new Derived(); ptr->func();`|Calls `Base::func()`|
|`Base* ptr = new Derived(); ptr->virtualFunc();`|Calls `Derived::virtualFunc()`|
|`delete basePointer` without virtual destructor|**Memory leak!**|

## 🎓 Simple Mental Model

- **Virtual = "Check what I'm actually pointing to at runtime"**


# References


## Closely Related Notes

- Abstract Function in C++

### Next:

### Prev:
