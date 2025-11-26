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

- **Class as blueprint**: `Car` class defines what all cars will have
    
- **Objects as instances**: `myCar` and `yourCar` are actual cars with their own data
    
- **Properties**: `brand`, `color`, `speed`
    
- **Behaviors**: `accelerate()`, `brake()`, `displayInfo()`

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
	
   // Getter methods
    std::string getBrand() const { return brand; }
    std::string getColor() const { return color; }
    int getSpeed() const { return speed; }
    
    // Setter methods  
    void setBrand(const std::string& newBrand) { brand = newBrand; }
    void setColor(const std::string& newColor) { color = newColor; }
	
}


int main()
{
	// Objects from the "Car" Class
	Car myCar;
	Car yourCar;
	
	// Use Objects
	myCar.setBrand("Toyota");
	myCar.setColor("Red");
	myCar.accelerate();
	myCar.displayInfo(); // Output: Toyota Red going 10 mph
    
    yourCar.setBrand("Honda");
    yourCar.setColor("Blue");
    yourCar.accelerate();
    yourCar.accelerate();
    yourCar.displayInfo();  // Output: Honda Blue going 20 mph
    
    return 0;
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

