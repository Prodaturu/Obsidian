**Created:** 02.12.25, 10:12

**Status:** #

**Hashtags:**
- #errorhandling 
- #compiletimeerrors
- #runtimeerrors
- #danglingpointers
- #logicalerrors

# Types of [[3 - Main Notes/C++/C++ Error Handling.md|Errors]] in C++

- Errors are classified into types depending on why and where the Error occurs

## 1. Compile-Time [[3 - Main Notes/C++/C++ Error Handling.md|Errors]]

- Errors preventing program from compiling
- Common Compile Time Errors:
	- Missing semicolon
	- Using undeclared variables
	- Mismatched types

#### Example: Compile Time [[3 - Main Notes/C++/C++ Error Handling.md|Error]]

```cpp
int x = 5 // Missing semi-colon
std::cout << y; // Undeclared y
int x = "Hello"; // Type Mismatch
```

## 2. Runtime [[3 - Main Notes/C++/C++ Error Handling.md|Errors]]

- Runtime errors occur when the program compiles but crashes or behaves unexpectedly
- Common Runtime Errors:
	- Dividing by zero
	- Accessing out-of-bounds array elements
	- Using deleted memory (dangling pointer)

#### Examples: Common Runtime [[3 - Main Notes/C++/C++ Error Handling.md|Errors]]

##### Un-computable logic
```cpp
int a = 10;
int b = 0;

int result = a/b; // Throws an error
std::cout << result;
```

##### Accessing out-of-bounds elements
```cpp
int members[3] = {1, 2, 3};
std::cout << nums[3]; // no element on index 3
```

##### Using Deleted memory
```cpp
int* ptr = new int(10);
delete ptr;
std::cout << *ptr; // danglling pointer
```

## 3. Linktime [[3 - Main Notes/C++/C++ Error Handling.md|Errors]]

- Occur during the **linking phase** after compilation
- When object files are combined into executable
- Common Link-time Errors:
	- Missing function definitions
	- Multiple definitions of same function
	- Library linking issues
	- Incorrect include paths

#### Example: Linktime [[3 - Main Notes/C++/C++ Error Handling.md|Error]]

```cpp
// File1.cpp
void functionA(); // Declaration only

// File2.cpp
int main()
{
	functionA(); // ERROR: functionA never defined
}
```

# References


## Closely Related Notes

- 

### Next:

### Prev:
