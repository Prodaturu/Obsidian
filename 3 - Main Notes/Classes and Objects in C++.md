**Created:** *26.11.25, 22:04*

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**
	- 

- **Topic Tags:**
	- [[OOPS in C++]]

# Classes and Objects

## Class

- **Class:** Blueprint / Template that defines properties and behaviours of the objects created from that class will have
	 
- Created using `class` keyword

### Syntax:

```C++
class ClassName
{
private:
	// Data members (attributes)
	type member1;
	type member2;

public:
	// Member Functions (methods)
	returnType functionName1(parameters);
	returnType functionName2(parameters);

}

```

#### Example:

```C++

class Car
{
private:
	std::string brand;
	std::string color;
	int         speed;
	
public:
	void accelerate()
	{
		speed += 10;
	}
	
	void brake()
	{
		speed -= 10;
	}
	
	void displayInfo()
	{
		std::cout << brand << " " << color << " going " << speed << " kmph" << std::endl;
	}
	
	//Getter methods
	
	
}

```

## Objects:

- 

### Creating an Object

```C++

class ExampleClass
{
public:
	int    num;
	strinf str;
};

```




# References


## Closely Related Notes

### Next:

### Prev:

