**Created:** *26.11.25, 21:08*

**Status:**

**Hashtags:**
- #CPP 
- #functions 
- #lambdafunctions

**Links / Tags:** 
- **Relevance Links:**
	- Functions in C++
	
- **Topic Tags:**
	- 
	  
---

# Lambda Functions

- *lambda function* also called as *lambda*
- Small, Anonymous function you can write directly in your code
- Perfect for short, one-off operations

### Syntax

`[capture-list] (parameters) -> return_type {// function body };`

- `[capture-list]`
	- Variables from outside scope that **lambda** can access
- `(parameters)`
	- list of parameters that **lambda** takes as input
- `return_type` 
	- (optional) type of the return value
- `{// function body}` 
	- the body of the function

#### Example 
```C++
int multiplier = 3;

auto times = [multiplier] (int x) {return (x * multiplier);};

std::cout << times(5) << std::endl;
```
- `[multiplier]`
	- 


# References:
