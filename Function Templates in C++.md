**Created:** 03.12.25, 05:24

**Status:** #atomic

**Hashtags:**
- #cpp
- #templates
- #generic_programming
- #functions
- #atomic

**Links / Tags:** 
- **Relevance Links:**
  - User-Defined Types in C++
  - Templates in C++

- **Topic Tags:**
  - #function_templates
  - #type_deduction
  - #compile_time_polymorphism

# Function Templates in C++

> Part of templates in C++.

Function templates let you write one function that works with many types. The compiler generates specific instances per type at **compile time**.

## Basic Syntax

```cpp
template <typename T>
T functionName(T parameter) {
    // Code using type T
}
