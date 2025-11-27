**Created:** 27.11.25, 20:50

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Abstract Classes

- **Definition**
	- Classes that **cannot be instantiated**
	- serve as interfaces for derived classes
- **Purpose**
	- Force derived classes to implement specific functionality

## Pure Virtual Function

```cpp
virtual void function() = 0; // Makes class abstract
```

## Key Points

- `= 0` $\Rightarrow$ Pure Virtual (no Implementation)
- Class becomes abstract
- cannot create objects of abstract class
- Derived classes must implement all pure virtual functions

## Examples:

#### Basic Abstract Class

```cpp
class Shape // Abstract Class
{
public:
	virtual void draw() = 0; // pure virtual
};

// Shape s; // ERROR: Cannot instantiate
```

#### Complete Implementation

```cpp
class Animal
{
public:
	virtual void speak = 0; // Must Implement
	virtual void sleep(){}  // Optional override
	void breathe() {}       // Inherited as-is
};

class Dog : public Animal
{
public:
    void speak() override   // MUST implement
    {
        cout << "Woof!" << endl;
    }
};

Dog dog;  // OK - implements all pure virtual functions
```

#### Practical Usage

```cpp

```

# References


## Closely Related Notes

### Next:

### Prev:
