**Created:** *<span class ="color-green">02.05.26, 15:16</span>*

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
	- #cpp #language #syntax 
- **Topic Tags:**
	- #lexing #tokens #sourcecode
	  
**Links / Tags:** 
- **Relevance Links:**
	- C++ Syntax and Structure
	
- **Topic Links:**
	- [[C++ Source Character Set]]
	- [[C++ Tokens]]
		- the ones below will be moved into Tokens note later on 
		- [[Keywords in C++]]
		- [[Identifiers in C++]]
		- [[Literals in C++]]
		- [[Operators and Punctuator Tokens in C++]]
		
	- [[Comments and Whitespaces in C++]]
	  
---

# C++ Lexical Structure

- C++ Lexical Structure describes the early reading stage of C++ source code
- At this stage:
	- source code is treated like plain text
	- this text is read as [[C++ Source Character Set|source characters]]
	- these [[C++ Source Character Set|source characters]] are then grouped into [[C++ Tokens|tokens]]
	- [[Comments and Whitespaces in C++|Spaces, newlines, and comments]] help:
		- making source code readable
		- separating source code into meaning pieces called [[C++ Tokens|tokens]]
	
- Example:
	-  ```cpp
int x = 5;
		```
	-  This can be understood as tokens like:
		- `int` -> keyword
		- `x` -> identifier
		- `=` -> operator / punctuator token
		- `5` -> literal
		- `;` -> punctuator 
	- See [[C++ Tokens]] for more in depth understanding
	  
- Lexical stage happens before C++ can understand higher level constructs like
	- expressions
	- statements
	- declarations
	- functions
	
---
## Synopsis
- C++ source code is written using readable [[C++ Source Character Set|source characters]]
- from which meaningful units called  [[C++ Tokens|tokens]] are formed
- while [[Comments and Whitespaces in C++|Spaces, newlines, and comments]] help with:
	- readability
	- token separation


---
# Related Notes
> Things you might want to think about alongside this note, but not because of it

---
# References
