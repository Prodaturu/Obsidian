**Created:** 27.11.25, 16:50

**Status:** #baby #incomplete

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**
	- OOPS in C++


# Polymorphism

- Polymorphism <=> "Many forms"
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

- Resolved during runtime
- **Function Overloading:**
	- 



# References


## Closely Related Notes

### Next:

### Prev:
