**Created:** *27.11.25, 04:48*

**Status:** #baby 

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**
	- 

- **Topic Tags:**
	- [[Classes and Objects in C++]]
	  
	  **Sub Tags:**
		- [[Encapsulation in C++]]


# Access Specifiers

- **Access Specifiers** control how the members (attributes and methods) of a class can be accessed
- Help in:
	- Protect data
	- Organise code
	- So only the right parts can be seen or changed


## Types of Access Specifiers

- There are 3 access specifiers in C++:
	- `public` 
		- Members are accessible from outside the class
	- `private`
		- Members cannot be accessed from outside the class
	- `protected` 
		- Members cannot be accessed from outside the class
		- But, can be accessed in inherited classes


### Public

- Members declared `public` :
	- can be accessed and modified from outside the class

### Private

- Members declared `private` :
	- can not be accessed or modified from outside the class
- **Default** type for members if no *access specifier* is specified

### Protected

- Members declared `protected`
	- cannot be accessed from outside the class
	- but can be accessed in child classes


## Notes on Access Specifiers

- It is possible to access `private` members of a class using `public` method inside the same class
	
- It is considered good practice to declare class attributes as `private` (as often as you can)
- This will reduce the possibility of messing up code
- Main ingredient of **Encapsulation**




# References


## Closely Related Notes

### Next:

### Prev:

