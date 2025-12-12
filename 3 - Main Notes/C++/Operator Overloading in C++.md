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

## Examples

```cpp
// returnType = `Car&`; operator_symbol = `=`; parameters = "(const Car& other)"
Car& operator=(const Car &other) {}

// returnType = `Vector`, operator_symbol = `+`, parameters = `(const Vector& other)`  
Vector operator+(const Vector& other) { }

// returnType = `bool`, operator_symbol = `==`, parameters = `(const Date& other)`
bool operator==(const Date& other) { }
```

## Key Rules and Limitations

- **Cannot create new operators** - only existing C++ operators
- **Cannot change operator precedence** - follows original rules
- **At least one operand must be user-defined type**
- **Some operators cannot be overloaded**: `::`, `.*`, `.`, `?:`, `sizeof`

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


---

## Related Notes

- Operators in C++ 
    
- Classes and Objects in C++ 
    
- Orthodox Canonical Form 
- Rule of Three Five Zero in C++

# External References

# Rough Notes on Topic

- 