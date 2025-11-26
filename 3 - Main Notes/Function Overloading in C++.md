**Created:** *26.11.25, 20:26*

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**
	- [[Function Overloading]]

- **Topic Tags:**
	- [[C++]]

# Function Overloading

#### Definition:

- Multiple function can have the same name
	- As long as their parameters are different in type or number
- Let's us use same function name for similar tasks

#### Examples:

1. **Without Function Overloading:**

```C++
int plusFuncInt(int x, int y) {  
  return x + y;  
}  
  
double plusFuncDouble(double x, double y) {  
  return x + y;  
}  
  
int main() {  
  int myNum1 = plusFuncInt(8, 5);  
  double myNum2 = plusFuncDouble(4.3, 6.26);  
  
  cout << "Int: " << myNum1 << "\n";  
  cout << "Double: " << myNum2;  
  return 0;  
}

```

2. **With Function Overloading:**

- Instead of defining two functions that should do the same thing
- It is better to overload one
	- `plusFunc` is overloaded here to work with both `int` and `double`

```C++
int plusFunc(int x, int y) {  
  return x + y;  
}  
  
double plusFunc(double x, double y) {  
  return x + y;  
}  
  
int main() {  
  int myNum1 = plusFunc(8, 5);  
  double myNum2 = plusFunc(4.3, 6.26);  
  
  cout << "Int: " << myNum1 << "\n";  
  cout << "Double: " << myNum2;  
  return 0;  
}

```




# References


## Closely Related Notes

### Next:

### Prev:

