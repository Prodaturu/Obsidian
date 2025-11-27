**Created:** *27.11.25, 04:21*

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**
	- [[Function Overloading in C++]]

- **Topic Tags:**
	- [[Classes and Objects in C++]]

# Constructor Overloading

## Definition:

- Can have more than one constructor in same class
	- This is called as **Constructor Overloading**
	  
- Each constructor must have 
	- Different number of parameters or
	- Different type of parameters
	
- The compiler knows which one to use when creating an object


## Why Use Constructor Overloading?

- To give flexibility when creating objects
- To set default or custom values
- To reduce repetitive code


## Example: Constructor with multiple Operators

```cpp

class Car
{
public:
	string _brand;
	string _model;
	
	Car()
	{
		_brand = "unknown";
		_model = "unknown";
	}
	
	Car(string brand, string model)
	{
		_brand = brand;
		_model = model;
	}
}

```


# References


## Closely Related Notes

### Next:

### Prev:

