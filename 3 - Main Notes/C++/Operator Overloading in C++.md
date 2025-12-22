**Created:** *27.11.25, 18:51*

**Status:** #map

**Hashtags:**
- **Relevance Tags:**
    - #cpp
    - #OOPS 
    - #operatoroverloading
- **Topic Tags:**
    - #polymorphism

**Links / Tags:** 
- **Relevance Links:**
    - Operators in C++               <!-- parent, plain text on purpose -->
    - Classes and Objects in C++     <!-- also related, plain text -->
    
- **Topic Links:**
	- [[General Rules for Operator Overloading]]
    - [[Copy Assignment Operator in C++]]
    - [[Overloading Arithmetic Operators in C++]]
    - [[Overloading Comparison Operators in C++]]
    - [[Overloading Stream Operators in C++]]
    - [[Member vs Non Member Operator Overloads in C++]]

---

# Operator Overloading in C++

## Definition and simple explanation
- **Definition:**
	- Let's us define the meaning of an operator when applied to operand(s) of a class type
	- Careful use of operator overloading can make our programs easier to write and read
	  
- In simple terms:
	- We tell C++ what `+`, `==`, `=`, `<<`, etc., should mean **for our own types**
	
- The `operator` keyword declares a function specifying
	- what an *operator symbol* means 
	- when applied to a class instance
	  
- Extends existing C++ operators
	- so they work with custom class objects in a meaningful way
	  
- Makes operators like `+`, `-`, `==`, etc. work with your own classes
    - by defining what these operations should do for your specific data types
    
- Goal: make custom types feel as natural to use as built-in types

```cpp
type operator operator_symbol (parameter_list)
```

## Syntax

- `returnType operator_symbol (parameters) {// Implementation}`
	- returnType $\Rightarrow$ What the operator returns
	- operator_symbol $\Rightarrow$ Operator being overloaded / defined for
		- The operator when used on the `class`; 
		- would do what is defined within the `//Implementation`
	- parameters $\Rightarrow$ Right hand operand

### Examples

```cpp
// returnType = `Car&`; operator_symbol = `=`; parameters = "(const Car& other)"
Car& operator=(const Car &other) {}

// returnType = `Vector`, operator_symbol = `+`, parameters = `(const Vector& other)`  
Vector operator+(const Vector& other) { }

// returnType = `bool`, operator_symbol = `==`, parameters = `(const Date& other)`
bool operator==(const Date& other) { }
```

## Why operator Overloading Exists

- Without operator overloading

```cpp
v1.add(v2);
```

- without operator overloading
```cpp
v1 + v2;
```

same logic - but the second is:
- more readable
- closer to mathematical intent
- consistent with built-in types

**Goal**
- Make user-defined types feel as natural as built-in ones

## What actually gets overloaded
- Operators are implemented as **functions**
- The keyword `operator` introduces the overload

General Form:
```cpp
return_type operator<symbol>(parameters)
{
	// Implementation
}
```

### Basic Examples:
```cpp
// Assignment
Car& operator=(const Car& other);

// Arithmetic
Vector operator*(const Vector& other);

// Comparison
bool operator==(const Date &other);
```

### Complete Example

**Step 1**: **Define a Class**
**Step 2:** **Overload required Operator**
```cpp
class Vector
{
public:
	int _x;
	int _y;
	
	vector(int x, int y) : _x(x), _y(y)
	{
	}
	
	int getx() const { return _x; }
	int gety() const { return _y; }
	
	Vector operator+(const Vector& other) const
	{
		return Vector(_x + other._x, _y + other._y);
	}
};
```
*Why this design is good:*
- `operator+` is a member function
- `const` -> does not modify either operand
- accessors keep data encapsulated

**Step 3**: **Use the overloaded Operator**
```cpp
Vector a(1, 2);
Vector b(3, 4);

Vector c = a + b; //result will be: (4, 6)
```

*What compiler actually does:*
- `a+b` is translated to `a.operator+(b)`
- Makes it clear that
	- `a` is the left hand operand
	- `b` is passed as a parameter
- The operator is just a function call

## Key Rules and Limitations
- **❌ Cannot create new operators** - only existing C++ operators
- **❌ Cannot change operator precedence** - follows original rules
- **✅ At least one operand must be user-defined type**
- **❌ Some operators cannot be overloaded**: `::`, `.*`, `.`, `?:`, `sizeof` etc.,

# Internal References

## Sub-notes
- [[General Rules for Operator Overloading]]
	Rules how overloaded operators can be implemented
	
- [[Copy Assignment Operator in C++]]  
    Special member function that can also be seen as an overloaded `operator=`.
    
- [[Overloading Arithmetic Operators in C++]]  
    Designing `+`, `-`, `*`, `/`, etc. for custom numeric-like types.
    
- [[Overloading Comparison Operators in C++]]  
    Designing `==`, `!=`, `<`, `>`, `<=`, `>=`.
    
- [[Overloading Stream Operators in C++]]  
    `operator<<` / `operator>>` for `std::ostream` and `std::istream`.
    
- [[Member vs Non Member Operator Overloads in C++]]  
    When to make an operator a member, and when to use a free function or friend.

# Operator overloading explained with code

- Consider the following class

```cpp

```
---

## Related Notes

- Operators in C++ 
    
- Classes and Objects in C++ 
    
- Orthodox Canonical Form 
- Rule of Three Five Zero in C++

# External References

# Rough Notes on Topic

- 