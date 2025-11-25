**Created:** *25.11.25, 19:33*

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**
	- [[Ternary Operators]]
	- [[if else statements]]
	- 

- **Topic Tags:**
	- [[C++]]

# Ternary Operator

- Short hand for `if... else` statements
- Known as **Ternary Operators**

- Returns a value based on condition
	- If condition is true, returns first value
	- If condition is false, returns second value

- **Syntax :**
	- `variable = (condition) ? expressionIfTrue : expressionIfFalse`
	
	- Example:
```C++
	int time = 20;
	string result = (time < 18) ? "Good day" : "Good evening"
```
-  The above expression is similar to the following if else statement
```C++
	int time = 20;
	
	if (time < 18)
	{
		string result = "Good day";
	}
	else
	{
		string result = "Good evening";
	}
```

- Ternary operator can also be used within the if... else statement

- When to use If... else or Ternary:
	- short and simple conditions : Ternary;
	- longer and more complex : if else;


# Nested Ternary

- Ternary Operators can be nested to handle more than 2 outcomes
	- Though it can make code harder to read

```C++
int time = 22;

string message = (time < 12) ? "Good morning"
	: (time < 18) ? "Good Afternoon"
	: "Good evening"

cout << message;
```
# References


## Closely Related Notes

### Next:

### Prev:

