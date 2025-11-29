**Created:** 27.11.25, 18:51

**Status:** #baby 

**Hashtags:**
- #CPP #OOPS #polymorphism #operatoroverloading 
  
**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Operator Overloading in C++

- Extending the functionality of existing C++ operators to work with custom class objects in a meaningful way
- Making operators like `+`, `-`, `==`, etc., work with your own classes
	- by defining what these operations should do for your specific data types.
- Makes custom types feel as natural and intuitive to use as built-in types.

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

# References



## Closely Related Notes

### Next:

### Prev:
