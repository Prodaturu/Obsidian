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

- `add<int>(5, 3)` tells the compiler to use `int` for `T`
- while `add<double>(2.5, 1.5)` tells it to use `double`.

## Class Templates

- Templates can be used to make classes that work with any data-type

### Syntax

``` cpp
template <typename T>
class ClassName { /* members and methods using T */ }
```

- `T` is the placeholder for a data type (like `int`, `float` , etc.,)
- `T` is common practice, but any name can be used

```cpp
Template <typename X>

X add(X a, X b) {return (a + b)};

int main
```

# References


## Closely Related Notes

### Next:

### Prev:
