**Created:** *<span class ="color-green">09.01.26, 03:16</span>*

**Note Type:** #map

**Hashtags:**
- **Relevance Tags:**
	- #math
	- #linearalgebra
	- #vectors
	- #aiengineer
- **Topic Tags:**
	- #features
	- #representations
	- #dimensions

**Links / Tags:** 
- **Relevance Links:**
	- Mathematics
	- Linear Algebra for AI
	- Vectors for AI
- **Topic Links:**
	- [[Vector Geometry & Similarity]]
	- [[Vector Representations in AI]]
---

# Vector Basics for AI

> Core meaning of **vectors as used in AI systems**.  
> This note covers concepts that usually **do not need further splitting**.

---

## 1. What a Vector Means in AI

In AI, a vector is:
- an ordered list of numbers
- representing **something concrete**:
  - a data point
  - a feature set
  - an embedding
  - a model output

A vector is **not**:
- an abstract mathematical object
- a direction-only geometric arrow (that intuition comes later)

---

## 2. Dimensionality

- vector length = number of features
- dimension = information capacity
- higher dimension ≠ better by default

In AI:
- dimensions are chosen or learned
- unused dimensions still affect computation
- dimensionality impacts:
  - similarity
  - generalization
  - efficiency

(High-dimensional effects are handled elsewhere.)

---

## 3. Feature Vectors vs Parameter Vectors

### Feature vectors
- represent inputs or intermediate representations
- examples:
  - image pixels
  - word embeddings
  - sensor readings

### Parameter vectors
- represent learnable values
- examples:
  - weights
  - biases
- usually not interpreted semantically

---

## 4. Single Vector vs Batch of Vectors

- single vector → one sample
- batch → matrix of vectors

In practice:
- models almost always operate on batches
- batching affects:
  - performance
  - numerical stability
  - gradient behavior

(This connects later to matrices.)

---

## 5. Ordering Matters

- vector positions are meaningful
- swapping entries changes meaning
- unlike sets or bags, vectors encode structure

This matters for:
- model correctness
- feature engineering
- embedding alignment

---

## Explicitly Out of Scope
- vector space axioms
- basis definitions
- coordinate-free formulations
- proofs

---

# Closely Related concepts
- Vector Geometry & Similarity
- Vector Representations in AI
- Matrices for AI

# External References
