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
	return (0);
}
```

### 🔍 Key Differences
|Aspect|Method 1 (Parameter)|Method 2 (Return Value)|
|---|---|---|
|**Syntax**|`time(&timestamp)`|`timestamp = time(NULL)`|
|**What's passed**|Address of variable|`NULL` pointer|
|**How value is obtained**|Written to parameter|Returned by function|
|**Common use**|Older C-style code|Modern C++ style|

### 💡 Simple Example (Both Methods)

```cpp
#include <iostream>
#include <ctime>

int main()
{
	// Method 1: Parameter-based
	time_t ts1; 
	time(&ts1);
	std::cout << "Method 1:" << ctime(&ts1);
	std::cout << "Method 2:" << ctime(&ts2);
	
	// Both produce identical output!
	return(0);
}
```



# References


## Closely Related Notes

### Next:

### Prev:
