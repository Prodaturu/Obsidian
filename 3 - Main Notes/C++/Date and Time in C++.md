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
	- `#include <ctime>`

## Current Date and Time Display

- `<ctime>` $\rightarrow$ library has a variety of functions to measure dates and times
- `time()` $\rightarrow$ function gives us a **timestamp** representing current date and time
- `ctime()`  $\rightarrow$ shows the date and time that a timestamp represents

#### Example
```cpp
// Get the timestamp to current date and time
time_t timestamp;
time(&timestamp);

// Display the date and time represented by the timestamp
cout << ctime(&timestamp);
```


# References


## Closely Related Notes

### Next:

### Prev:
