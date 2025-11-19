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

| Example          | LaTeX Code       | Description                  |         |                    |
| ---------------- | ---------------- | ---------------------------- | ------- | ------------------ |
| $A \cup B$       | `\cup`           | Union                        |         |                    |
| $A \cap B$       | `\cap`           | Intersection                 |         |                    |
| $A \setminus B$  | `\setminus`      | Set difference               |         |                    |
| $A - B$          | `A - B`          | Set difference (alternative) |         |                    |
| $\overline{A}$   | `\overline{A}`   | Complement                   |         |                    |
| $A^c$            | `A^c`            | Complement (alternative)     |         |                    |
| $A \times B$     | `\times`         | Cartesian product            |         |                    |
| $                | A                | $                            | `\|A\|` | Cardinality of set |
| $\mathcal{P}(A)$ | `\mathcal{P}(A)` | Power set                    |         |                    |
| $2^A$            | `2^A`            | Power set (alternative)      |         |                    |

## Logic & Quantifiers

| Example           | LaTeX Code    | Description           |
| ----------------- | ------------- | --------------------- |
| $\forall x$       | `\forall`     | For all               |
| $\exists x$       | `\exists`     | There exists          |
| $\exists! x$      | `\exists!`    | There exists unique   |
| $P \implies Q$    | `\implies`    | Implies               |
| $P \rightarrow Q$ | `\rightarrow` | Implies (alternative) |
| $P \iff Q$        | `\iff`        | If and only if        |
| $\neg P$          | `\neg`        | Not / negation        |
| $\land$           | `\land`       | Logical AND           |
| $\lor$            | `\lor`        | Logical OR            |
| $\top$            | `\top`        | True                  |
| $\bot$            | `\bot`        | False                 |

## Strings & Languages

| Example          | LaTeX Code       | Description                |         |                  |
| ---------------- | ---------------- | -------------------------- | ------- | ---------------- |
| $\Sigma$         | `\Sigma`         | Alphabet                   |         |                  |
| $\Sigma^*$       | `\Sigma^*`       | Kleene star                |         |                  |
| $\Sigma^+$       | `\Sigma^+`       | Kleene plus                |         |                  |
| $w \in \Sigma^*$ | `w \in \Sigma^*` | String over alphabet       |         |                  |
| $\varepsilon$    | `\varepsilon`    | Empty string               |         |                  |
| $\lambda$        | `\lambda`        | Empty string (alternative) |         |                  |
| $                | w                | $                          | `\|w\|` | Length of string |
| $xy$             | `xy`             | Concatenation              |         |                  |
| $x \cdot y$      | `x \cdot y`      | Concatenation (explicit)   |         |                  |
| $L^*$            | `L^*`            | Kleene star of language    |         |                  |
| $L_1 \circ L_2$  | `L_1 \circ L_2`  | Concatenation of languages |         |                  |

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

| Example        | LaTeX Code     | Description            |
| -------------- | -------------- | ---------------------- |
| $A \leq_m B$   | `A \leq_m B`   | Many-one reduction     |
| $A \leq_T B$   | `A \leq_T B`   | Turing reduction       |
| $A \equiv_m B$ | `A \equiv_m B` | Many-one equivalence   |
| $\text{ATM}$   | `\text{ATM}`   | A_TM (Halting problem) |

## Arrow Symbols

| Example              | LaTeX Code           | Description                  |
| -------------------- | -------------------- | ---------------------------- |
| $\to$                | `\to`                | Right arrow (functions)      |
| $\rightarrow$        | `\rightarrow`        | Right arrow                  |
| $\gets$              | `\gets`              | Left arrow                   |
| $\leftarrow$         | `\leftarrow`         | Left arrow                   |
| $\mapsto$            | `\mapsto`            | Maps to                      |
| $\longrightarrow$    | `\longrightarrow`    | Long right arrow             |
| $\longleftarrow$     | `\longleftarrow`     | Long left arrow              |
| $\Rightarrow$        | `\Rightarrow`        | Double right arrow (implies) |
| $\Leftarrow$         | `\Leftarrow`         | Double left arrow            |
| $\Leftrightarrow$    | `\Leftrightarrow`    | Double left-right arrow      |
| $\iff$               | `\iff`               | If and only if               |
| $\uparrow$           | `\uparrow`           | Up arrow                     |
| $\downarrow$         | `\downarrow`         | Down arrow                   |
| $\updownarrow$       | `\updownarrow`       | Up-down arrow                |
| $\Uparrow$           | `\Uparrow`           | Double up arrow              |
| $\Downarrow$         | `\Downarrow`         | Double down arrow            |
| $\Updownarrow$       | `\Updownarrow`       | Double up-down arrow         |
| $\nearrow$           | `\nearrow`           | North-east arrow             |
| $\searrow$           | `\searrow`           | South-east arrow             |
| $\swarrow$           | `\swarrow`           | South-west arrow             |
| $\nwarrow$           | `\nwarrow`           | North-west arrow             |
| $\hookrightarrow$    | `\hookrightarrow`    | Hook right arrow             |
| $\hookleftarrow$     | `\hookleftarrow`     | Hook left arrow              |
| $\leftharpoonup$     | `\leftharpoonup`     | Left harpoon up              |
| $\rightharpoonup$    | `\rightharpoonup`    | Right harpoon up             |
| $\rightleftharpoons$ | `\rightleftharpoons` | Right-left harpoons          |
| $\leadsto$           | `\leadsto`           | Leads to                     |
| $\rightsquigarrow$   | `\rightsquigarrow`   | Squiggly right arrow         |

## Multiplication Symbols

|Example|LaTeX Code|Description|
|---|---|---|
|$a \times b$|`\times`|Cross product / multiplication|
|$a \cdot b$|`\cdot`|Dot product / multiplication|
|$ab$|`ab`|Implicit multiplication|
|$a * b$|`a * b`|Asterisk multiplication|
|$a(b)$|`a(b)`|Implicit with parentheses|
|$a \ast b$|`\ast`|Asterisk symbol|

## Geometry & Trigonometry Symbols

| Example         | LaTeX Code      | Description            |
| --------------- | --------------- | ---------------------- |
| $\angle ABC$    | `\angle ABC`    | Angle                  |
| $\triangle ABC$ | `\triangle ABC` | Triangle               |
| $\perp$         | `\perp`         | Perpendicular          |
| $\parallel$     | `\parallel`     | Parallel               |
| $\nparallel$    | `\nparallel`    | Not parallel           |
| $\sim$          | `\sim`          | Similar to             |
| $\cong$         | `\cong`         | Congruent to           |
| $\simeq$        | `\simeq`        | Approximately equal to |
| $\sin x$        | `\sin x`        | Sine                   |
| $\cos x$        | `\cos x`        | Cosine                 |
| $\tan x$        | `\tan x`        | Tangent                |
| $\csc x$        | `\csc x`        | Cosecant               |
| $\sec x$        | `\sec x`        | Secant                 |
| $\cot x$        | `\cot x`        | Cotangent              |
| $\arcsin x$     | `\arcsin x`     | Inverse sine           |
| $\arccos x$     | `\arccos x`     | Inverse cosine         |
| $\arctan x$     | `\arctan x`     | Inverse tangent        |
| $90^\circ$      | `90^\circ`      | Degrees                |
| $\pi$           | `\pi`           | Pi                     |
| $\theta$        | `\theta`        | Theta (angle)          |
| $\phi$          | `\phi`          | Phi (angle)            |

## Additional Useful Symbols

| Example             | LaTeX Code          | Description               |
| ------------------- | ------------------- | ------------------------- |
| $\aleph_0$          | `\aleph_0`          | Countable infinity        |
| $\mathfrak{c}$      | `\mathfrak{c}`      | Cardinality of continuum  |
| $\binom{n}{k}$      | `\binom{n}{k}`      | Binomial coefficient      |
| $\lfloor x \rfloor$ | `\lfloor x \rfloor` | Floor function            |
| $\lceil x \rceil$   | `\lceil x \rceil`   | Ceiling function          |
| $\approx$           | `\approx`           | Approximately equal       |
| $\sim$              | `\sim`              | Asymptotically equivalent |
| $\propto$           | `\propto`           | Proportional to           |
| $\infty$            | `\infty`            | Infinity                  |

## Greek Letters in LaTeX

### Lowercase Greek Letters

|Example|LaTeX Code|Letter Name|
|---|---|---|
|$\alpha$|`\alpha`|Alpha|
|$\beta$|`\beta`|Beta|
|$\gamma$|`\gamma`|Gamma|
|$\delta$|`\delta`|Delta|
|$\epsilon$|`\epsilon`|Epsilon|
|$\varepsilon$|`\varepsilon`|Epsilon (variant)|
|$\zeta$|`\zeta`|Zeta|
|$\eta$|`\eta`|Eta|
|$\theta$|`\theta`|Theta|
|$\vartheta$|`\vartheta`|Theta (variant)|
|$\iota$|`\iota`|Iota|
|$\kappa$|`\kappa`|Kappa|
|$\lambda$|`\lambda`|Lambda|
|$\mu$|`\mu`|Mu|
|$\nu$|`\nu`|Nu|
|$\xi$|`\xi`|Xi|
|$\pi$|`\pi`|Pi|
|$\varpi$|`\varpi`|Pi (variant)|
|$\rho$|`\rho`|Rho|
|$\varrho$|`\varrho`|Rho (variant)|
|$\sigma$|`\sigma`|Sigma|
|$\varsigma$|`\varsigma`|Sigma (final)|
|$\tau$|`\tau`|Tau|
|$\upsilon$|`\upsilon`|Upsilon|
|$\phi$|`\phi`|Phi|
|$\varphi$|`\varphi`|Phi (variant)|
|$\chi$|`\chi`|Chi|
|$\psi$|`\psi`|Psi|
|$\omega$|`\omega`|Omega|

### Uppercase Greek Letters

| Example    | LaTeX Code | Letter Name |
| ---------- | ---------- | ----------- |
| $\Delta$   | `\Delta`   | Delta       |
| $\Gamma$   | `\Gamma`   | Gamma       |
| $\Lambda$  | `\Lambda`  | Lambda      |
| $\Omega$   | `\Omega`   | Omega       |
| $\Phi$     | `\Phi`     | Phi         |
| $\Pi$      | `\Pi`      | Pi          |
| $\Psi$     | `\Psi`     | Psi         |
| $\Sigma$   | `\Sigma`   | Sigma       |
| $\Theta$   | `\Theta`   | Theta       |
| $\Upsilon$ | `\Upsilon` | Upsilon     |
| $\Xi$      | `\Xi`      | Xi          |


## Formatting Tips for Obsidian:

- Use `$...$` for inline math: `$A \subseteq B$`
    
- Use `$$...$$` for display math: `$$A \subseteq B$$`
    
- Use `\text{...}` for text within math: `$\text{such that}$`
    
- Common packages automatically available in Obsidian: amsmath, amssymb, amsthm
    
- ### Example Proof Usage:
    
- Assume $P \implies Q$ and $P$ is true.
    
-  $\because this$  $\implies$  $\therefore that$ must be true  
- 
$\square$  $\leftarrow$ Square
