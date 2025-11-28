**Created:** 28.11.25, 03:52

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Templates

- Templates lets us write a function or class that works with different data types
- Help avoid repeating code and make programs more flexible

## Function Templates

- Can be created using `template` keyword

### Syntax
```cpp
template <typename T>
return_type function_name(T parameter) { /* code */ }
```

- `T` is a placeholder for a data type (like `int`, `float`, etc.)
- Any name instead of `T`, `T` is just common practice

### Example

```cpp
template <typename T>
T add(T a, T b) {return (a + b);}

int main()
{
	cout << add<int>(5, 3) << endl;
	cout << add<double>(2.5, 7.5) << endl;
	return 0;
}
```



# References


## Closely Related Notes

### Next:

### Prev:
