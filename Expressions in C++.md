**Created:** *<span class ="color-green">01.05.26, 03:30</span>*

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
    - #cpp
    - #language 
    - #semantics 
	
- **Topic Tags:**
	- #expressions 
	  
**Links:** 
- **Relevance Links:**
	- Expressions and Operators in C++
	
- **Topic Links:**
	- [[Expressions vs Statements in C++]]
	- [[Expression Evaluation in C++]]
	- [[Value Categories in C++]]
	- [[Side effects in Expressions in C++]]
	- [[Implicit and Explicit Conversions in Expressions]]
	  
---

# Expressions in C++

- Sequence of *operators* and / or *operands*, that specifies a computation
- Anything that *produces a value* or *performs an action* is called an **expression**
- So anything C++ can evaluate is an Expression
- Examples:
	  - `x + 3`
	  - `x`
	  -  `std::cout << x`
	
- All of the above examples are Expressions as they are valid things that can be evaluated by C++
- Expressions are different from statements or instructions
	- In depth distinction at [[Expressions vs Statements in C++]]

---

## What can Expressions do?

- An expression can:
	- Produce a value
		- `3`
		- `x + 3`
	- Perform an action
		- `std::cout << x`
	- combine smaller expressions into a bigger expression
		- `(x + 3) * (x + 2)`
		- here `x`, `3`,`x + 3` etc.; are all valid expressions

---
## Expression Evaluation

- Process of computing the value of an expression
- C++ has its specific rules in evaluating an expression
  
  Discussed in: [[Expression Evaluation in C++]]

---
## Expression Characteristics

- Every C++ expression can be characterised by 2 independent properties
	- non-reference type
	- primary value category
	  
- 

---
# Related Notes
> Things you might want to think about alongside this note, but not because of it

---
# References
