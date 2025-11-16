status: #teen 

tags: [[Latex]]

# LaTeX Symbols Cheat Sheet


## Set Theory Symbols

| Example             | LaTeX Code              | Description                 |
| ------------------- | ----------------------- | --------------------------- |
| $x \in A$           | `\in`                   | Element of / belongs to     |
| $x \notin A$        | `\notin`                | Not an element of           |
| ${a, b, c}$         | `\{a, b, c\}`           | Set                         |
| ${, x \mid P(x) ,}$ | `\{\, x \mid P(x) \,\}` | Set builder notation        |
| $A \subseteq B$     | `\subseteq`             | Subset or equal to          |
| $A \subset B$       | `\subset`               | Proper subset               |
| $A \subsetneq B$    | `\subsetneq`            | Proper subset (alternative) |
| $\emptyset$         | `\emptyset`             | Empty set / null set        |
| $\varnothing$       | `\varnothing`           | Empty set (alternative)     |
| $\mathbb{N}$        | `\mathbb{N}`            | Natural numbers             |
| $\mathbb{Z}$        | `\mathbb{Z}`            | Integers                    |
| $\mathbb{Q}$        | `\mathbb{Q}`            | Rational numbers            |
| $\mathbb{R}$        | `\mathbb{R}`            | Real numbers                |
| $\mathbb{C}$        | `\mathbb{C}`            | Complex numbers             |

## Set Operations

|Example|LaTeX Code|Description|
|---|---|---|
|$A \cup B$|`\cup`|Union|
|$A \cap B$|`\cap`|Intersection|
|$A \setminus B$|`\setminus`|Set difference|
|$A - B$|`A - B`|Set difference (alternative)|
|$\overline{A}$|`\overline{A}`|Complement|
|$A^c$|`A^c`|Complement (alternative)|
|$A \times B$|`\times`|Cartesian product|
|$|A|$|`\|A\|`|Cardinality of set|
|$\mathcal{P}(A)$|`\mathcal{P}(A)`|Power set|
|$2^A$|`2^A`|Power set (alternative)|

## Logic & Quantifiers

|Example|LaTeX Code|Description|
|---|---|---|
|$\forall x$|`\forall`|For all|
|$\exists x$|`\exists`|There exists|
|$\exists! x$|`\exists!`|There exists unique|
|$P \implies Q$|`\implies`|Implies|
|$P \rightarrow Q$|`\rightarrow`|Implies (alternative)|
|$P \iff Q$|`\iff`|If and only if|
|$\neg P$|`\neg`|Not / negation|
|$\land$|`\land`|Logical AND|
|$\lor$|`\lor`|Logical OR|
|$\top$|`\top`|True|
|$\bot$|`\bot`|False|

## Strings & Languages

|Example|LaTeX Code|Description|
|---|---|---|
|$\Sigma$|`\Sigma`|Alphabet|
|$\Sigma^*$|`\Sigma^*`|Kleene star|
|$\Sigma^+$|`\Sigma^+`|Kleene plus|
|$w \in \Sigma^*$|`w \in \Sigma^*`|String over alphabet|
|$\varepsilon$|`\varepsilon`|Empty string|
|$\lambda$|`\lambda`|Empty string (alternative)|
|$|w|$|`\|w\|`|Length of string|
|$xy$|`xy`|Concatenation|
|$x \cdot y$|`x \cdot y`|Concatenation (explicit)|
|$L^*$|`L^*`|Kleene star of language|
|$L_1 \circ L_2$|`L_1 \circ L_2`|Concatenation of languages|

## Automata Theory

|Example|LaTeX Code|Description|
|---|---|---|
|$M = (Q, \Sigma, \delta, q_0, F)$|`M = (Q, \Sigma, \delta, q_0, F)`|DFA definition|
|$\delta(q, a)$|`\delta(q, a)`|Transition function|
|$\hat{\delta}(q, w)$|`\hat{\delta}(q, w)`|Extended transition function|
|$L(M)$|`L(M)`|Language of automaton|
|$\varepsilon$-NFA|`\varepsilon`-NFA|Epsilon-NFA|

## Regular Expressions

|Example|LaTeX Code|Description|
|---|---|---|
|$a \mid b$|`a \mid b`|Union / OR|
|$ab$|`ab`|Concatenation|
|$a^*$|`a^*`|Kleene star|
|$(a \mid b)^*$|`(a \mid b)^*`|Complex expression|
|$a^+$|`a^+`|One or more repetitions|
|$a?$|`a?`|Zero or one occurrence|

## Context-Free Grammars

|Example|LaTeX Code|Description|
|---|---|---|
|$G = (V, \Sigma, R, S)$|`G = (V, \Sigma, R, S)`|CFG definition|
|$A \to \alpha$|`A \to \alpha`|Production rule|
|$A \rightarrow \alpha$|`A \rightarrow \alpha`|Production (alternative)|
|$\alpha \Rightarrow \beta$|`\alpha \Rightarrow \beta`|Derivation step|
|$\alpha \Rightarrow^* \beta$|`\alpha \Rightarrow^* \beta`|Zero or more derivation steps|
|$L(G)$|`L(G)`|Language of grammar|

## Pushdown Automata

|Example|LaTeX Code|Description|
|---|---|---|
|$M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$|`M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)`|PDA definition|
|$\delta(q, a, X)$|`\delta(q, a, X)`|PDA transition|

## Turing Machines

|Example|LaTeX Code|Description|
|---|---|---|
|$M = (Q, \Sigma, \Gamma, \delta, q_0, q_a, q_r)$|`M = (Q, \Sigma, \Gamma, \delta, q_0, q_a, q_r)`|TM definition|
|$\delta(q, a)$|`\delta(q, a)`|TM transition function|
|$u q a v$|`u q a v`|TM configuration|
|$\vdash$|`\vdash`|Yields / computation step|
|$\vdash^*$|`\vdash^*`|Zero or more computation steps|

## Complexity Theory

|Example|LaTeX Code|Description|
|---|---|---|
|$\mathbf{P}$|`\mathbf{P}`|Complexity class P|
|$\mathbf{NP}$|`\mathbf{NP}`|Complexity class NP|
|$\mathbf{PSPACE}$|`\mathbf{PSPACE}`|Complexity class PSPACE|
|$\mathbf{EXP}$|`\mathbf{EXP}`|Complexity class EXP|
|$\mathbf{coNP}$|`\mathbf{coNP}`|Complexity class co-NP|
|$O(n)$|`O(n)`|Big O notation|
|$\Omega(n)$|`\Omega(n)`|Big Omega notation|
|$\Theta(n)$|`\Theta(n)`|Big Theta notation|
|$o(n)$|`o(n)`|Little o notation|
|$\omega(n)$|`\omega(n)`|Little omega notation|

## Reducibility & Computability

|Example|LaTeX Code|Description|
|---|---|---|
|$A \leq_m B$|`A \leq_m B`|Many-one reduction|
|$A \leq_T B$|`A \leq_T B`|Turing reduction|
|$A \equiv_m B$|`A \equiv_m B`|Many-one equivalence|
|$\text{ATM}$|`\text{ATM}`|A_TM (Halting problem)|

## Additional Useful Symbols

|Example|LaTeX Code|Description|
|---|---|---|
|$\aleph_0$|`\aleph_0`|Countable infinity|
|$\mathfrak{c}$|`\mathfrak{c}`|Cardinality of continuum|
|$\binom{n}{k}$|`\binom{n}{k}`|Binomial coefficient|
|$\lfloor x \rfloor$|`\lfloor x \rfloor`|Floor function|
|$\lceil x \rceil$|`\lceil x \rceil`|Ceiling function|
|$\approx$|`\approx`|Approximately equal|
|$\sim$|`\sim`|Asymptotically equivalent|
|$\propto$|`\propto`|Proportional to|
|$\infty$|`\infty`|Infinity|

## Formatting Tips for Obsidian:

- Use `$...$` for inline math: `$A \subseteq B$`
    
- Use `$$...$$` for display math: `$$A \subseteq B$$`
    
- Use `\text{...}` for text within math: `$\text{such that}$`
    
- Common packages automatically available in Obsidian: amsmath, amssymb, amsthm
    
- ### Example Proof Usage:
    
- Assume $P \implies Q$ and $P$ is true.
    
-  $\because this$  $\implies$  $\therefore that$ must be true  
- 
$\square$

Now you have a complete logic and proof section with all the essential symbols for mathematical reasoning and proof writing!