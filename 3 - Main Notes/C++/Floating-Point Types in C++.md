**Created:** 03.12.25, 01:53

**Status:** #atomic

- **Hashtags:**
	- #cpp
	- #datatypes
	- #atomic
	- #numeric

**Links / Tags:** 
- **Relevance Links:**
	- Primitive Integral Types in C++
	- [[Special Types in C++]]
	- [[IEE754]]

- **Topic Tags:**
	- #floatingpoint
	- #precision
	- #rounding
	- #ieee754

# Floating-Point Types in C++

> Part of C++ data types.

Floating-point types represent real numbers with fractional parts, but with limited precision.

## Types

- `float` – single-precision (usually 32-bit)  
- `double` – double-precision (usually 64-bit, default choice)  
- `long double` – extended precision (implementation-dependent)

## Key ideas

- **Precision vs range**  
  - `float` has less precision, more rounding error.  
  - `double` is usually enough for most numeric work.  
  - `long double` can be used when you really need more precision.

- **Rounding and error**  
  - Many decimal fractions can’t be represented exactly.  
  - Comparisons should often use a tolerance (epsilon), not `==`.

- **Use cases**  
  - Geometry, physics, approximations → `double`.  
  - Graphics, large arrays where memory matters → sometimes `float`.

# References

- 
