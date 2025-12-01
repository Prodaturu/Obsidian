**Created:** 29.11.25, 15:44

**Status:** #

**Hashtags:**
- #CPP 
- #files

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Files

- The `fstream` library allows us to work with files
- `fstream` requires to include
	1. `<iostream>` header
	2. `<fstream>` header

### Example

```cpp
#include <iostream>
#include <fstream>

// This is how you would include / import for using the "fstream" library
```

- There are 3 classes included in the `fstream` library
- which are used to create, write or read files

| Class      | Description                                                                 |
| ---------- | --------------------------------------------------------------------------- |
| `ofstream` | Creates and writes to files                                                 |
| `ifstream` | Reads from files                                                            |
| `fstream`  | A combination of ofstream and ifstream: creates, reads, and writes to files |

## Create and Write To a File

- To create a file:
	- use either the `ofstream` or `fstream` class
	- and specify the name of the file.
- To write to the file
	- use the insertion operator (`<<`).

### Example

```cpp
#include <iostream>  
#include <fstream>  
using namespace std;  
  
int main() {  
  // Create and open a text file  
  ofstream MyFile("filename.txt");  
  
  // Write to the file  
  MyFile << "Files can be tricky, but it is fun enough!";  
  
  // Close the file  
  MyFile.close();  
}
```

### Why do we close the file?

- It is considered good practice
- It  cleans up unnecessary memory space.

## Read a File

- To read from a file
	- use either the `ifstream` or `fstream` class
	- and the name of the file.

**Note:** 
- We also use a `while` loop together with the `getline()` function
	- (which belongs to the `ifstream` class) to read the file line by line
	- and then we can print the content of the file:

### Example

```cpp
// Create a text string, which is used to output the text file  
string myText;  

// Read from the text file  
ifstream MyReadFile("filename.txt");  

// Use a while loop together with the getline() function to read the file line by line  
while (getline (MyReadFile, myText))
{  
	// Output the text from the file  
	cout << myText;
}
// Close the file  
MyReadFile.close();
```

## Exercises

- Which C++ library allows us to work with files?
	- `filestreams`
	- `fstream`
	- `string`
	- `vector`
- **Answer:** `fstream`

- Which class from `fstream` library is used to create and write to files?
	- `ifstream`
	- `ofstream`
	- `fstream`
	- `filemanager`
- **Answer:** 
  
  
# References

## Closely Related Notes

### Next:

### Prev:
