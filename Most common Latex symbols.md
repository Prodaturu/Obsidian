
2025-11-16 01:22

Status:

Tags:

------------------------------------------------------------------------
# Most common Latex symbols

## ===== BASIC SET NOTATION =====

x $\in$ A

$\{a, b, c\}$

$\{\, x \mid \text{condition on } x \,\}$

x $\notin$ A

A $\subseteq$ B

A $\subset$ B

$\emptyset$

$\Sigma^{*}$

$\mathbb{N}$

$\mathbb{Z}$

$\mathbb{R}$

  

% ===== SET OPERATIONS =====

$A \cup B$

A $\cap$ B

A $-$ B

$A^{c}$

A $\times$ B

$\mathcal{P}(A)$

  

% ===== STRINGS & LANGUAGES =====

$\Sigma$

$w \in \Sigma^{*}$

$\varepsilon$

$|w|$

$xy$

$x \cdot y$

$\Sigma^{*}$

$L^{*}$

$L = \{\, w \in \Sigma^{*} \mid \text{property of } w \,\}$

$0^{n}1^{n}$

$a^{i}b^{j}c^{k}$

  

% ===== FINITE AUTOMATA (DFA/NFA) =====

$M = (Q, \Sigma, \delta, q_{0}, F)$

$\delta : Q \times \Sigma \to Q$

$\delta : Q \times \Sigma \to \mathcal{P}(Q)$

$\hat{\delta}(q, w)$

$L(M)$

$\varepsilon$-transition

  

% ===== REGULAR EXPRESSIONS =====

$a | b$

$ab$

$a^{*}$

$(a | b)^{*}$

  

% ===== CLOSURE PROPERTIES =====

$L_{1} \cup L_{2}$

$L_{1} \cap L_{2}$

$L_{1}L_{2}$

$L_{1}^{*}$

$\overline{L_{1}}$

  

% ===== PUMPING LEMMA =====

$\forall z \in L,\ |z| \ge p \Rightarrow$

$z = uvw,\ |uv| \le p,\ |v| \ge 1,\ \forall i \ge 0,\ uv^{i}w \in L$

  

% ===== CONTEXT-FREE GRAMMARS =====

$G = (V, \Sigma, R, S)$

$A \to aB$

$A \to \varepsilon$

$A \Rightarrow w$

$A \Rightarrow^{*} w$

$L(G)$

  

% ===== PUSHdown AUTOMATA (PDA) =====

$M = (Q, \Sigma, \Gamma, \delta, q_{0}, Z_{0}, F)$

$\delta : Q \times \Sigma_{\varepsilon} \times \Gamma_{\varepsilon} \to \mathcal{P}(Q \times \Gamma_{\varepsilon})$

  

% ===== TURING MACHINES =====

$M = (Q, \Sigma, \Gamma, \delta, q_{0}, q_{\text{accept}}, q_{\text{reject}})$

$\delta : Q \times \Gamma \to Q \times \Gamma \times \{L, R\}$

$u q v$

$L(M)$

  

% ===== DECIDABILITY & COMPUTABILITY =====

$\text{A is decidable}$

$\text{A is Turing-recognizable}$

$A \leq_{m} B$

  

% ===== COMPLEXITY CLASSES =====

$\mathbf{P}$

$\mathbf{NP}$

$\mathbf{PSPACE}$

$V(x, y)$

# References



-----------------------------------------------------------------------
