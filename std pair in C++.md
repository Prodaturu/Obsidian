**Created:** 06.12.25, 11:57

**Status:** #atomic

**Hashtags:**

- #CPP  
- #genericprogramming
- #datatypes


**Links / Tags:**

- **Relevance Links:**
    
    - Generic Types in C++ <!-- parent, plain text on purpose -->
    - C++ Data Types <!-- parent, plain text on purpose -->
    - Templates in C++ <!-- template mechanism, plain text -->
        
    - [[std tuple in C++]]
    
- **Topic Tags:**
    
    - #stdpair
    - #twovalues
    - #simpletuple

# std::pair in C++

> Part of generic types in C++.

- `std::pair<T, U>` stores **two related values**, possibly with different types.
	
- It is a small, generic struct with:
    
    - `first` – first value
    - `second` – second value

## Basic Usage

```cpp
#include <utility>
#include <string>
#include <iostream>
using namespace std;

int main()
{
    pair<string, int> person("John", 25);

    cout << person.first  << endl;   // "John"
    cout << person.second << endl;   // 25
}
```

## Returning multiple values

- You can use `std::pair` as a simple return type:

```cpp
pair<bool, int> findValue()
{
    // found?  value
    return {true, 42};
}

int main()
{
    auto result = findValue();
    
    if (result.first)
    {
        cout << "Value: " << result.second << endl;
    }
}

```