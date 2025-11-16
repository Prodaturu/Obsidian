
2025-11-16 01:22

Status:

Tags:

------------------------------------------------------------------------
# Most common Latex symbols
### Sets

`\{a, b, c\} \{\, x \mid \text{condition on } x \,\}`

### Membership

x $\in$ A 
x $\notin$ A`

### Subsets

`A \subseteq B A \subset B`

### Empty & universal set

`\emptyset \Sigma^{*}`

### Common sets

`\mathbb{N} \mathbb{Z} \mathbb{R}`

---

# ✅ **2. Set Operations**

`A \cup B A \cap B A - B A^{c} A \times B`

### Power set

`\mathcal{P}(A)`

---

# ✅ **3. Strings & Languages (Sipser-style)**

### Alphabet, string, empty string

`\Sigma w \in \Sigma^{*} \varepsilon`

### Length of a string

`|w|`

### Concatenation

`xy x \cdot y`

### Kleene star

`\Sigma^{*} L^{*}`

### Language definitions

`L = \{\, w \in \Sigma^{*} \mid \text{property of } w \,\}`

### Pattern/exponent notation (VERY common)

`0^{n}1^{n} a^{i}b^{j}c^{k}`

---

# ✅ **4. Finite Automata (DFA/NFA)**

### Machine definition

`M = (Q, \Sigma, \delta, q_{0}, F)`

### Transition function

`\delta : Q \times \Sigma \to Q        % DFA \delta : Q \times \Sigma \to \mathcal{P}(Q)  % NFA`

### Extended transition function

`\hat{\delta}(q, w)`

### Language of a machine

`L(M)`

### ε-transitions

`\varepsilon \varepsilon\text{-transition}`

---

# ✅ **5. Regular Expressions**

`a | b ab a^{*} (a | b)^{*}`

---

# ✅ **6. Closure Properties**

`L_{1} \cup L_{2} L_{1} \cap L_{2} L_{1}L_{2} L_{1}^{*} \overline{L_{1}}`

---

# ✅ **7. Pumping Lemma for Regular Languages**

`\forall z \in L,\ |z| \ge p \Rightarrow  z = uvw,\ \ |uv| \le p,\ \ |v| \ge 1,\ \ \forall i \ge 0,\ uv^{i}w \in L`

---

# ✅ **8. Context-Free Grammars (CFGs)**

### Grammar definition

`G = (V, \Sigma, R, S)`

### Production rules

`A \to aB A \to \varepsilon`

### Derivations

`A \Rightarrow w A \Rightarrow^{*} w`

### Language of grammar

`L(G)`

---

# ✅ **9. Pushdown Automata (PDA)**

### PDA definition

`M = (Q, \Sigma, \Gamma, \delta, q_{0}, Z_{0}, F)`

### Transition function

`\delta : Q \times \Sigma_{\varepsilon} \times \Gamma_{\varepsilon}           \to \mathcal{P}(Q \times \Gamma_{\varepsilon})`

---

# ✅ **10. Turing Machines**

### TM definition

`M = (Q, \Sigma, \Gamma, \delta, q_{0}, q_{\text{accept}}, q_{\text{reject}})`

### Transition function

`\delta : Q \times \Gamma \to Q \times \Gamma \times \{L, R\}`

### Configurations

`u q v`

### Language of a TM

`L(M)`

---

# ✅ **11. Decidability & Computability**

### Decidable language notation

`\text{A is decidable}`

### Recognizable language

`\text{A is Turing-recognizable}`

### Mapping reductions

`A \leq_{m} B`

---

# ✅ **12. Complexity (P, NP)**

### Big complexity classes

`\mathbf{P} \mathbf{NP} \mathbf{PSPACE}`

### Polynomial-time verifier

`V(x, y)`
# References



-----------------------------------------------------------------------
