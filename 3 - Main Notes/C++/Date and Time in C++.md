**Created:** 01.12.25, 18:18

**Status:** #

**Hashtags:**
- #CPP 
- #Time 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Date and Time in C++

- The `ctime` library allows us to work with dates and times
- To use it,
	- You must import `<ctime>` header file:

```cpp
// Import the data/time library

#include <ctime>
```

## Display Current Date and Time

- `time()` - Gets current timestamp
- `ctime()` - Converts timestamp to readable string

## ⚡ Two ways to use "time()" function

### 1. Using Parameter (Traditional):

- Passing address to store the timestamp
- The traditional way of doing things

```cpp
#include <iostream>
#include <ctime>
int main()
{
	// Get the timestamp to current date and time
	time_t timestamp; // declare a time stamp variable
	time(&timestamp); // pass ADDRESS to store timestamp
	
	// Display the date and time represented by the timestamp
	cout << ctime(&timestamp); // Output: "Mon Dec 1 22:57:45 2025"
	return (0);
}
```

### 2. Using Return Value (Modern)

```cpp
#include <iostream>
#include <ctime>

int main()
{
	time_t timestamp = time(NULL);  // pass NULL, get RETURN value
	std::cout << ctime(&timestamp); // Display: "Mon Dec 1 22:59:42 2025"
}
```


# References


## Closely Related Notes

### Next:

### Prev:
