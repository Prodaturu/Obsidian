**Created:** 27.11.25, 18:47

**Status:** #atomic 

**Hashtags:**
- #CPP 
- #pointers
- #mathematical-foundations 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**
	- [[Ternary Operators in C++]]
	- [[Operator precedence in C++]]
	- [[Operator Overloading in C++]]

# Operators in C++

- Symbols that perform operations on operands.

## Operator Categories

1. **Arithmetic Operators**: 
	1. Operations used for performing calculations in C++
	2. `+`, `-`, `*`, `/`, `%`
    
2. **Relational Operators**:
	1. Compare 2 values & return bool values depending on comparison
	2. `==`, `!=`, `<`, `>`, `<=`, `>=`
    
3. **Logical Operators**:
	1. Logical operators are used for combining multiple conditions or bool values
	2. `&&`, `||`, `!`
    
4. **Assignment Operators**:
	1. Assignment operators are used to assign values to variables
	2. `=`, `+=`, `-=`, `*=`, `/=`
    
5. **Bitwise Operators**:
	1. Perform operations at the bit level
	2. `&`, `|`, `^`, `~`, `<<`, `>>`
	   
6. **Pointer Operators**:
	1. Used to work with memory addresses
	2. `&`, `*`
	   
7. **Memory Management Operators**:
	1. Used for memory management
	2. `new`, `delete`, `new[]`, `delete[]`
	   
8. **Type Casting Operators**:
	1. Used to convert one data to another
	2. `static_cast`, `dynamic_cast`, `const_cast`, `reinterpret_cast`
	   
9. **Comma Operator**:
	1. Allows multiple expressions in a single statement
	2. `,`
     
10. **Other**:
	1. `++`, `--`, `?:`, `::`, `.*`, `->` , `->*`

## Key Sub-topics:

- **Operator Precedence in C++** - Order of evaluation
    
- **Operator Overloading in C++** - Custom operator behaviour
    
- **Ternary Operators in C++** - Conditional operator

## Basic Examples:

```cpp

int a = 5, b = 3;
int sum = a + b;        // Arithmetic
bool result = (a > b);  // Relational  

a += 2;                 // Assignment

```

## The `->` Operator in C++

- The `->` operator is used to access members (like functions or variables) through a [pointer](https://www.w3schools.com/cpp/cpp_pointers.asp).
- It's a shortcut for writing `(*pointer).member`
- If using a pointer to an object
	- `->` is used to access its members.

# References
