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


## 2. Capture by value - `[=]`, `[...]`

#### `[=]` -> capture used variables by value
```cpp
int a = 1;
int b = 2;

auto f = [=] ()
{
	//
	// a and b are copied into the lambda
	std::cout << a + b << "\n";
};
```
- each used outer variable is **copied**
- inside lambda you see **const-like copy**
	- by default

#### `[...]` -> capture a specific variables by value
```cpp
int x = 10;
int y = 20;

auto f = [x]()
{
	std::cout << x << "\n";
	// y not captured -> cannot use y
};
```
- only `x` is captured
- useful when you want to be explicit and avoid surprises

## 3. Capture by reference - `[&]`, `[&x, &y, ...]`

#### `[&]` -> Capture used variables by reference
```cpp
let counter = 0;

auto inc = [&] ()
{
	++counter; //modifies original counter
};

inc();
std::cout << counter; // 1
```
- outer variables are not copied
- lambda works on **original** values

#### `[&x, &y, ...]` -> Capture given variables by reference
```cpp
int x = 10;
int y = 20;

auto f = [&x] ()
{
	x += 5;   // modifies original x
	// y not captured -> can't use y
}
```

- Capturing by reference is a bit dangerous
	- the lambda **outlives** the variables (e.g. stored and used later)
	- you then have **dangling reference**


## 4. Mixed Captures - `[x, &y, ...]`

- We can mix value and reference captures:
```cpp
int x = 10;
int y = 20;

auto f = [x, &y] ()
{
	// x is a copy
	// y is a reference
	
	std::cout << x << ", " << y << "\n";
	y++;
};
```
- `x` stays same outside, `y` changes


## 5. Initialiser Captures (C++14) - `[z = x + y]`

- We can create a new captured variable:

```cpp
int x = 2;
int y = 3;

auto f = [z = x + y] ()
{
	std::cout << z << "\n";
};
```
- `z` is a new variable inside the lambda
- initialised with `x + y` at the moment of capture

##### Useful to move-only things
```cpp
auto ptr = std::make_unique<int>(42);

auto f = [p = std::move(ptr)]()
{
	std::cout << *p << "\n";
};
```


## 6. Capturing `this`

- Inside a member function:
```cpp
class counter
{
private:
	int value = 0;
	
public:
	void run()
	{
		auto inc = [this]()
		{
			value++;
		}
		
		inc();
	}
};
```
- `[this]` captures the **this pointer**
- lambda can access `value` and other members

# Quick Cheat Sheet

# External References
