**Created:** 27.11.25, 14:06

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**
	- OOPS in C++


# Inheritance

- Allows a class to reuse attributes and methods from another class
	
- Can be grouped into 2 categories
	- **derived class** (child)
		- Class that inherits from another class
	- **base class** (parent)
		- Class being inherited from
	
- To inherit from a class, we use `:`
- The `Child` class inherits the attributes and methods from the `Parent` class

### Example

```cpp
// Parent / Base Class
class Vehicle
{
public:
	string brand = "Ford";
	
	void honk()
	{
		cout << "Tuut, Tuut!" << endl;
	}
};

// Derived Class
Class Car: public Vehicle
{
public:
	string model = "Mustang";
};

int main()
{
	Car myCar;
	
	myCar.honk();
	cout << myCar.brand + " " + myCar.model;
	
	return (0);
}

```


## Advantages of Inheritance

- Useful for code re-usability:
	- reuse attributes and methods of existing class
	- Directly when creating a new Class

# Multi - level Inheritance

- Class can also be derived from a class that's derived from another class
	
- Class A -> Class B (Intermediate - derived from A) -> Class C (Most derived - derived from B)

## Key Points

- Chain of Inheritance:
	- A -> B -> C
- C gets features from both B and A
- If B inherits from A, and C inherits from B, then C also inherits from A
- Constructor calls follow the chain: A-> B -> C
- Access rules apply at each levels

## Inheritance Flow

- Chain of Inheritance:
	- Animal -> Mammal -> Dog
	 
- Dog (Most derived) can access:
	- Animal's protected/public + Mammals protected/public + all its own
	
- Animal can access:
	- all its own
	  
- Main can access:
	- Public members of any class

### Example 




# References


## Closely Related Notes

### Next:

### Prev:
