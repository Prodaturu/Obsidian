**Created:** 27.11.25, 13:41

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**
	- [[Lambda Functions in C++]]
	- [[Function Overloading in C++]]


# Functions in C++

- A function is a block of code which only runs when it is called.

- You can pass data, known as parameters, into a function.

- Functions are used to perform:
	- certain actions
	- important for reusing code:
		- Define the code once, and use it many times.


## Create a Function

- C++ provides some pre-defined functions, such as `main()` which is used to execute code. 
- Can also create own functions to perform certain actions.
	
- To create (often referred to as _declare_) a function:
	- specify the name of the function, followed by parentheses **()**:

### Syntax

```cpp
void _myFunction_()
{  
  // code to be executed  
}  
```

#### Example Explained

- `myFunction()` is the name of the function
- `void` means that the function does not have a return value. You will learn more about return values later in the next chapter
- inside the function (the body), add code that defines what the function should do


## Call a Function

- Declared functions are not executed immediately.
	- They are "saved for later use"
	- will be executed later, when they are called.
	
- To call a function:
	- write the function's name followed by two parentheses `()` and a semicolon `;`
	
- In the following example, `myFunction()` is used to print a text (the action), when it is called

### Example

```cpp
Inside `main`, call `myFunction()`:

// Create a function  
void myFunction() {  
  cout << "I just got executed!";  
}  
  
int main() {  
  **myFunction();** // call the function  
  return 0;  
}  
  
// Outputs "I just got executed!"  
```

- A function can be called multiple times:

### Example

```cpp
void myFunction() {  
  cout << "I just got executed!\n";  
}  
  
int main() {  
  myFunction();
  myFunction();
  myFunction();

  return 0;  
}

/* Output:-

I just got executed!  
I just got executed!  
I just got executed!  

*/
```
  

## Function Declaration and Definition

- A C++ function consists of 2 parts:
	- **Declaration:** the return type, the name of the function, and parameters (if any)
	- **Definition:** the body of the function (code to be executed)

```cpp

void **myFunction()** { // **declaration**  
  // the body of the function (**definition**)  

}  
```

- **Note:**
	- If a user-defined function, such as `myFunction()` is declared after the `main()` function, **an error will occur**:
	- unless *forward declared*

### Example

```cpp
int main() {  
  myFunction();  
  return 0;  
}  
  
void myFunction() {  
  cout << "I just got executed!";  
}  

/*
Error 
*/
```


### Forward Declaration / Function Prototyping

- It is possible to separate the declaration and the definition of the function - for code optimisation.
	
- C++ programs can have function declaration above `main()`, and function definition below `main()`. This will make the code better organised and easier to read:

### Example

// **Function declaration**  
void myFunction();  
  
// The main method  
int main() {  
  myFunction();  // **call** the function  
  return 0;  
}  
  
// **Function definition**  
void myFunction() {  
  cout << "I just got executed!";  
}


# References


## Closely Related Notes

### Next:

### Prev:
