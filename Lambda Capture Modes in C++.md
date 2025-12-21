**Created:** *<span class ="color-green">21.12.25, 23:27</span>*

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
	- #cpp 
	- #functions 
	- #lambdafunctions 
- **Topic Tags:**
	- #captures 
	- #capturemodes
	- #moderncpp 

**Links / Tags:** 
- **Relevance Links:**
	- Lambda Functions in C++
- **Topic Links:**
	- 

---

# Lambda Capture Modes in C++

> How a lambda sees and uses variables from the surrounding scope

- Capture list is the `[...]` part at start of Lambda

```cpp
[capture-list] (parameters) {/* body */};
```

- It tells the Lambda **which variables** it is allowed to use and **how** it gets them 
	- by value or by reference


## 1. Capture nothing - `[]`
- `[]` -> captures nothing

```cpp
int x = 9;

auto f = [] ()
{
	// Cannot use x here - not captured
};
```
- safest form
- lambda can only see:
	- its own **parameters**
	- global/static variables
- we use this when the lambda does not need outer variables


## 2. Capture by value - `[=]` and `[x]`

- `[=]` -> capture used variables by value

```cpp
int a = 1;
int b = 2;

auto f = [=] ()
{
	// a and b are copied into the lambda
	std::cout << a + b << "\n";
};
```
- each used outer variable is **copied**
- inside lambda you see **const-like copy**
	- by default


# External References
