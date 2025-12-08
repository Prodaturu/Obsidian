**Created:** *<span class ="color-green">08.12.25, 08:59</span>*

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

# Compile-Time Errors

- **Definition:**
	
- An error that the compiler finds before the program runs
- Stops the build and must be fixed before code can be executed

## Why do compiler-time errors occur?

#### 1. Syntax Errors

- If we broke the **basic rules** of C++.
	- Forgot a semicolon.
	- Forgot a closing brace.
    - Wrote something the compiler cannot read.
    
- Think of it like **bad grammar** in a sentence.

#### 2. Type Mistakes

- Trying to use wrong kind of data
	- Assigning to a number
	- `double` where an `int` was expected
- Think of it like putting a US charger in an European power socket

#### 3. Name Resolution Error

- Calling a undeclared variable
- Incorrect variable name

#### 4. Wrong Function Call

- Too many / Too few arguments in function call
- Wrong types
- Compiler can't find a version that matches what we wrote

#### 5. Template Issues

- Templates allow any type
	- but not all types support all operations
	- Doing `x++` on a `string`

#### 6. 'access' / 'const' Violations

- Trying to change something marked as `const`
- Trying to access a private variable from outside the class

# Internal References



# External References
