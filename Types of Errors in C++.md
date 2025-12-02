**Created:** 02.12.25, 10:12

**Status:** #

**Hashtags:**
- #errorhandling 
- #compiletimeerrors
- #runtimeerrrors
- #danglingpointers

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Types of Errors in C++

- Errors are classified into types depending on why and where the Error occurs

## 1. Common Compile-Time Errors

- Errors preventing program from compiling
- Common Compile Time Errors:
	- Missing semicolon
	- Using undeclared variables
	- Mismatched types

#### Example: Compile Time Errors

```cpp
int x = 5 // Missing semi-colon
std::cout << y; // Undeclared y
int x = "Hello"; // Type Mismatch
```

## 2. Common Runtime Errors

- Runtime errors occur when the program compiles but crashes or behaves unexpectedly
- Common Runtime Errors:
	- Dividing by zero
	- Accessing out-of-bounds array elements
	- Using deleted memory (dangling pointer)

#### Example: Runtime [[3 - Main Notes/C++/C++ Error Handling.md|Errors]]

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

# References


## Closely Related Notes

- C+

### Next:

### Prev:
