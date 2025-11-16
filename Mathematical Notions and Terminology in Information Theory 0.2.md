
2025-11-15 21:41

Status: #baby

Tags: 
- [[Information Theory]] 
- [[Introduction to Information Theory 0]] 
- [[Mathematics]]

pages: 3 - 16 

------------------------------------------------------------------------
# Mathematical Notions and Terminology in Information Theory - 0.2

## Sets
- Group of objects represented as a unit
- Can contain any type of object, symbols, and even other sets\
- **Member:**  Objects in a set
- **Notation** : {1, 2, 3, 4} - example of a set
- $\in$ -> membership and $\notin$ -> non - membership

### Properties
- The order of describing set elements doesn't matter
- The repetition of a sets members doesn't matter

### Subset
- A is subset of B (**A $\subseteq$ B**) if every member of A is also a member of B

### Proper Subset
- A is a **proper subset** of B (**A $\subsetneq$ B**) if A is a subset of B and is not equal to B
- Example:
	- A = {1, 2, 3, 4}
	- B = {1, 2, 3, 4, 5}
	- $\because$ A is a subset of B (A $\subseteq$ B) and A is not equal to B (A $\neq$ B) => A $\subsetneq$ B

### Multiset
- Sets in which number of occurrences of members is taken into account
- {7} , {7, 7} are different as multisets but same as sets

### Infinite Set
- Has infinitely may elements
- we use the "..." notation to mean -> "continue the sequence forever"
- Example:
	1. Set of 'natural numbers (N)' -> {1, 2, 3, ...}
	2. Set of 'integers (Z)' -> { ..., -2, -1, 0, 1, 2, 3, ... }

### Empty Set
- A set with no elements / 0 elements is called an **empty set**
- Denoted as $\emptyset$

### Power set
- Set of all subsets of a Set A is called as the <span class="color-green">Power Set of A</span>
- **example:** 
	- Consider $A$  = $\{0, 1\}$
	- Subsets of $A$  are $\emptyset$, $\{0\}$, $\{1\}$, $\{0, 1\}$
	- The set of all subsets of $A$ => Let it be $B$ = $\{\emptyset, \{0\}, \{1\}, \{0, 1\}\}$
	- Then  Power set of $A$ =  $\mathcal{P}(A)$ = $B$ 

### Describing a Set
- There are 10 ways or more ways to describe a set
	1. Roster Notation
	2. Set-Builder Notation
	3. Predicate-Only Notation
	4. Interval Notation
	5. Describing with words
	6. Recursive Definition
	7. Definition by construction
	8. Power Set Notation
	9. Cartesian Product Form
	10. Comprehension with Multiple Conditions

#### Most Common Set Descriptions:

##### 1. Roster Form
- Used when sets are small and finite
- Examples:
	1. A = {1, 3, 5}
	2. Y = {$q_1$, $q_2$}

##### 2. Set-Builder /Comprehension Notation
- Used mainly for Infinite, rule-based sets
- General Form:
	- {x | condition on x}
	- example: 
		1. {X | X $\in$ $\mathbb{N}$  } 

##### 3. Pattern Form (Languages) / Mathematical Descriptions
- Very common for languages
- { $9^{n}$ | $n$ $>$ $0$ }

## Sequences and Tuples
- **Definition:** List of objects in some order
- Order and repetition of objects matters in  a Sequence
- Example: 
	- $(a, b, c)$ and $(c, a , b)$ are not the same Sequence
	- $(a, a, b, c)$ and $(a , b, c)$ are not the same Sequence

### Tuples
- **Definition:** A finite sequence is also called as a *tuple*
- A sequence with <span class="color-green">k</span> elements is called a <span class="color-green">k-tuple</span>
- A 2-tuple is also called a <span class="color-green">pair</span>
- Sets and Sequences may appear as elements of other sets and sequences

### Cross Product - Cartesian Product
- Consider $A$ and $B$ are two sets, 
- **Definition:** Set of all pairs where the first element is a member of $A$ and the second member is a member of $B$
- **Notation:** $A \times B$ <=> <span class="color-orange">Cartesian Product</span> or <span class="color-orange">Cross Product</span> of $A$ and $B$
- Example:
	- $A$  = $\{1, 2\}$, $B$  = $\{x, y, z\}$
	- $A \times B$ = $\{(1, x), (1, y), (1, z), (2, x), (2, y), (2, z)\}$

- We can also take <span class="color-orange">Cartesian Product</span> of a ***k*** Sets, $A_1$, $A_2$, ...., $A_k$, written as $A_1$ X $A_2$ X .... X $A_k$
	- It will be a set consisting of <span class="color-orange">k-tuples</span> $(a_1, a_2, ...., a_k)$ where $a_i \in A_i$

- If we have <span class="color-orange">Cartesian Product</span> of a set with itself
	- we can use the shorthand $A \times A \times A \times ... _{ktimes} ...$ = $A^K$
		- example: $A \times A \times A = A^3$

## Functions and Relations

- **Definition:** <span class="color-green">Function</span> or a <span class="color-green">Mapping</span> is an 
	- <span class="color-orange">Object</span> that sets up an <span class="color-orange">input-output relationship</span>
- A function takes Input and gives Output
	- Same Input always should produce same Output
- **Notation:** A function $f$ whose input is $a$ and output is $b$ 
	- $f(a) = b$

- Example: 
	- The Absolute value function $abs$ takes a number $x$ as input & return $x$ if positive or $-x$ if negative
		- $\therefore$ $abs(2) = abs(-2) = 2$

- ### Domain
	- 

------------------------------------------------------------------------
# References





# Related Links

## Exercises - 

## Prev - [[Automata Complexity and Computability 0.1]]

## Next - 