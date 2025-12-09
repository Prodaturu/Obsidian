**Created:** *25.11.25, 20:46*

**Status:** #atomic

**Hashtags:**

- **Relevance Tags:**
    
    - #cpp
    - #switchstatements
    - #conditionalstatements
    - #controlflow
    
- **Topic Tags:**
    
    - #branches
    - #break
    - #default
    - #fallthrough


**Links / Tags:**

- **Relevance Links:**
    - Control Flow in C++ <!-- parent -->
    - C++ Language Features <!-- higher-level parent -->
    
- **Topic Links:**
    - [[If else in C++]]
    - [[Break and Continue in C++]]


# Switch Statements in C++

`switch` is used to select **one of many code blocks** based on the value of an expression.

## How switch works

- the `switch` expression is evaluated once
    
- its value is compared with each `case` label
    
- when a match is found, execution jumps to that `case`
    
- from there it continues **downwards** until:
    
    - a `break` is hit, or
        
    - the `switch` block ends
        
- `break` and `default` are **optional**, but very important in practice
### Example usage:

```c++
int day = 4;

switch (day) 
{
	case 1:
		cout << "monday";
		break;
	case 2:
		cout << "tuesday";
		break;
	case 3:
		cout << "wednesady";
		break;
	case 4:
		cout << "Thursday";
		break;
	case 5:
		cout << "Friday";  
	    break;  
	case 6:  
	    cout << "Saturday";  
	    break;  
	case 7:  
	    cout << "Sunday";  
	    break;
}

// Output : "Thursday"

```

