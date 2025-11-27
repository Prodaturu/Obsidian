**Created:** *26.11.25, 21:08*

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**
	- 

- **Topic Tags:**
	- 


# Lambda Functions

- Small, Anonymous function you can write directly in your code
- Perfect for short, one-off operations

### Syntax

`[capture] (parameters) -> return_type {// function body };`

- `[capture]` - Variables from outside the **lambda** can access
- `(parameters)` - list of parameters that **lambda** takes as input
- `return_type` - (optional) type of the return value
- `{// function body}` - the body of the function 

#### Example 

```C++
int multiplier = 3;

auto times = [multiplier] (int x) {return (x * multiplier);};

std::cout << times(5) << std::endl;

```


# References


## Closely Related Notes

### Next:

### Prev:

