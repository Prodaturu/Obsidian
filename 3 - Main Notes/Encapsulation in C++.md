**Created:** *27.11.25, 06:01*

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**
	- 

- **Topic Tags:**
	- 

# Encapsulation

- Helps making sure that "sensitive" data is hidden from users
- To achieve this,
	- class variables/attributes must be declared `private` 
	- These can not be accessed from outside the class
	
- To allow others to read or modify the value of a `private` member
	- public **get** and **set** methods must be provided


## Accessing Private Members

- To access a private attribute
	- `public` "get" and "set" methods are declared

### Example: Accessing Private Members

```cpp
#include <iostream>
using namespace std;

class Emplloyee
{
private:
	int salary; // Private attribute
	
public:
	// setter function
	void setSalary(int newSalary)
	{
		salary = newSalary;
	}
	// getter function
	int getSalary()
	{
		return salary;
	}
};

int main()
{
	Employee myObj;
	myObj.setSalary(50000);
	cout << myObj.getSalary();
	
	return 0;
}
```

- `salary` is `private`
- `setSalary()` sets the value
- `getSalary()` returns the value

- We use `myObj.setSalary(5000)` to assign a value
- then `myObj.getSalary()` is used to print the value

## Why Use Encapsulation

- Ensures better control of data
- Can change one part of code without affecting other parts
- Increased security of data 




# References


## Closely Related Notes

### Next:

### Prev:

