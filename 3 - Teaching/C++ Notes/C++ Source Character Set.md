**Created:** *<span class ="color-green">03.05.26, 00:51</span>*

**Note Type:** #atomic 

**Hashtags:**
- **Relevance Tags:**
	- #cpp #language #syntax 
- **Topic Tags:**
	- #sourcecharacters #characterset #lexing
	  
**Links / Tags:** 
- **Relevance Links:**
	- C++ Lexical Structure
- **Topic Links:**
	- [[Source File Encoding in C++]]
	
---
# C++ Source Character Set

- Set of characters allowed to use directly when writing C++ source code
- These are the rawest building blocks:
	- Before the compiler groups anything into tokens (like `int` or `42`)
	- Compiler looks at the file as a sequence of source characters
	
---
## What characters can you write?

- The C++ standard defines a *basic source character set* that every conforming compiler must accept
- It consists of
	- 52 letters
	- 10 digits
	- 29 punctuation and special characters
	- 5 whitespace characters
	
- These is everything needed to write
	- keywords
	- identifiers
	- literals
	- operators
	
---
## What about characters not in the basic set?

- If a character is not in the basic source character set like `ü` or an emoji
- we have 2 options to use it in the source code
	- Rely on compiler's extended source character support
		- platform dependent, not portable
	- use a UCN (Universal Character Name)
		- portable way to write any Unicode character using only basic source characters
		- `\uNNNN` or `\UNNNNNNNN` (where N are hex digits)
		- UCNs are translated into the equivalent character inside the compiler
			- so writing `u00FC` is same as writing `ü` in a context where it's allowed
		- see [[Source File Encoding in C++]] for more on how
			- physical bytes in a file map to these source characters
		
	
---
# Related Notes

> Things you might want to think about alongside this note, but not because of it

- Unicode
- Character encoding
---
# References
