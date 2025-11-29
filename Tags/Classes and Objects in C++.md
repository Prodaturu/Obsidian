**Created:** *26.11.25, 22:04*

**Status:** 

**Hashtags:**
- #CPP 
- #cppclasses 
- #accessspecifiers

**Links / Tags:** 
- **Relevance Links:**
	- OOPS in C++

- **Topic Tags:**
	- [[Constructors in C++]]
	- [[Methods in C++]]
	- [[Access Specifiers in C++]]
	- [[Abstract Classes in C++]]
	- [[Templates in C++]]


# Classes

## Definition

- **Class**: A user-defined data type that acts as a blueprint for creating objects
    
- It bundles data (attributes) and functions (methods) that operate on that data
    
- Created using the `class` keyword

## Access Specifiers

- **private**: Accessible only within the class (default)
    
- **public**: Accessible from anywhere
    
- **protected**: Accessible within the class and its derived classes

## Basic Syntax

```cpp
class ClassName
{
private:
    // Private data members and functions
    // Accessible only within the class
    
public:
    // Public data members and functions  
    // Accessible from anywhere
    
protected:
    // Protected members
    // Accessible within class and derived classes
};
```

## Class Components

### 1. Data Members (Attributes/Properties)

- Variables that belong to the class
    
- Store the state of objects
    

### 2. Member Functions (Methods/Behaviors)

- Functions that belong to the class
    
- Define what objects can do


## Simple Class Example

```c++
#include <iostream>
#include <string>

// Class Definition - just the blueprint
class Student {
private:
    // Data members (attributes)
    std::string name;
    int age;
    double gpa;

public:
    // Member function declarations
    // These just say what students CAN do
    void displayInfo();
    void study(int hours);
    void setGrade(double grade);
    
    // Getter function declarations
    std::string getName();
    int getAge();
    double getGPA();
};

```

## Class Implementation

```cpp
// Implementing the member functions
// This is where we define WHAT the functions actually do

void Student::displayInfo() {
    std::cout << "Name: " << name << std::endl;
    std::cout << "Age: " << age << std::endl;
    std::cout << "GPA: " << gpa << std::endl;
}

void Student::study(int hours) {
    std::cout << name << " is studying for " << hours << " hours" << std::endl;
}

void Student::setGrade(double grade) {
    gpa = grade;
}

std::string Student::getName() {
    return name;
}

int Student::getAge() {
    return age;
}

double Student::getGPA() {
    return gpa;
}
```

## Key Points About Classes

- A class is just a **template** - it doesn't store actual data
    
- No memory is allocated when we define a class
    
- The class defines **what** properties and behaviors its future objects will have
    
- We can think of a class like a "cookie cutter" - it defines the shape but isn't a cookie itself


# Objects

## Definition

- **Object**: An actual instance of a class
    
- When we create an object, memory is allocated for its data members
    
- Each object has its own copy of the class's data members

## Creating Objects

```cpp

// Now we create actual objects from the Student class
int main() {
    // Creating objects (instances) of Student class
    Student student1;  // student1 is an object
    Student student2;  // student2 is another object
    
    // Each object has its own separate data
    // We'll learn how to use them in the next section
}
```

### Example problem

- **Question:**
- Create a class called `Book` with the following attributes:
	- `title` (`string`)
	- `author` (`string`)
	- `year` (`int`)
- Then create two objects of the `Book` class and print their attribute values.

```c++
#include <iostream>
#include <string>
using namespace std;

class Book
{
public:
	std::string title;
	std::string author;
	int         year;
}

int main()
{
	Book book1;
	
	book1.title = "Matilda";  
	book1.author = "Roald Dahl";  
	book1.year = 1988;  
	
	Book book2;  
	book2.title = "The Giving Tree";  
	book2.author = "Shel Silverstein";  
	book2.year = 1964;  
	
	cout << book1.title << ", by " << book1.author << ", " << book1.year << "\n";  
	cout << book2.title << ", by " << book2.author << ", " << book2.year;  
	return 0;
}
```


# Next Topic:


---
---
# References

## Closely Related Notes

### Next: 

