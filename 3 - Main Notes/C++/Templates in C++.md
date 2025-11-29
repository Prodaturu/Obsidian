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

# Function Templates

- Can be created using `template` keyword

### Syntax
```cpp
template <typename T>
return_type function_name(T parameter) { /* code */ }
```

- `T` is the placeholder for a data type (like `int`, `float` , etc.,)
- `T` is common practice, but any name can be used

### Example 1

```cpp
Template <typename X>

X add(X a, X b) {return (a + b);}

int main() {
	cout << add<int>(5 + 15) << endl;
	cout << add<double>(12.5 + 7.5) << endl;
	return (0);
}
```

- `add<int>(5 + 15)`
	- `<int>` says the compiler to use `int` for `X` as datatype
	- then performs the `add` function with `5`, `15` of `int` type as parameters
- `add<double>(12.5 + 7.5)`
	- `<double>` says the compiler to use `double` for `X` as datatype
	- then performs the `add` function with `12.5`, `7.5` of `double` type as parameters


### Example 2

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

# Class Templates

- Templates can be used to make classes that work with any data-type

### Syntax

``` cpp
template <typename T>
class ClassName { /* members and methods using T */ }
```

### Example 1

```cpp
template <typename T>

class Box
{
private:
	T value;
public:	
	Box(T v) {value = v;}
	void show() { cout << "value: " << value << endl;}
};

int main()
{
	Box<int> intBox(50);
	Box<string> strBox("Hello");
	
	intBox.show();
	strBox.show();
	return 0;
}
```

- `Box` is the "Template class"
	- it can store and display a value of any datatype
- In the `main` function 
	- `Box<int> intBox(50);` 
		- `<int>` replaces the template type `T`
		- Then creates a `int` value `50` in a class named `intBox`
	- `Box<string> strBox("Hello");`		
		- `<string>` replaces the template type `T`
		- Then creates a `string` value `"Hello"` in a class named `strBox`
	- `intBox.show();`
		- displays the `int` value `50` by replacing `T` with `int`
	- 

# References


## Closely Related Notes

### Next:

### Prev:
