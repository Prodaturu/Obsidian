**Created:**  *<span class ="color-green">09.01.26, 03:49</span>*

**Note Type:** #map

**Hashtags:**
- **Relevance Tags:**
    - #aiengineer
    - #map
- **Topic Tags:**
    - #inference
    - #serving
    - #systems
    - #latency
    - #deployment
      
**Links / Tags:**
- **Relevance Links:**
    - AI Engineer
    
- **Topic Links:**
    - [[Inference in AI Systems]]
    - [[Serving Systems for AI Models]]
    
---

# Inference & Serving Systems

> How trained AI models are **run, exposed, and operated** inside real-world systems.

- This axis explains what happens **after a model is trained**:
	- how predictions are actually produced
	- how models are made available to users or other systems
	- how performance, cost, and reliability are managed at runtime
	  
- If training is *learning*, this axis is *using what was learned*.
- You should read this axis if you want to understand:
	- how inference works in practice
	- why latency and throughput matter
	- how models become APIs and services
	- what can go wrong when models run in production


## 1. Inference (runtime execution)

> What happens when a trained model is executed.

- [[Inference in AI Systems]]

Talks about:

- runtime execution
- latency vs throughput
- state and context
- output behaviour
- failure visibility
---

## 2. Serving (system exposure)
> How inference is exposed, scaled, and operated.

- [[Serving Systems for AI Models]]

Talks about:
- request handling
- deployment topology
- scaling strategies 
- availability guarantees
---

## 3. Interfaces and Integration
> Boundary between inference systems and external callers.

- [[Model Interfaces and APIs]]
---

## 4. Resource, Cost, and Reliability

> Cross-cutting runtime constraints.

- [[Resource Management for Inference]]
- [[Cost Models for Inference]]
- [[Failure Modes in Inference Systems]]
---

# Related Notes

> Contextually adjacent, not owned here

- Data Foundations for AI    
- Systems Design for AI
- MLOps
- Model Lifecycle for AI Systems
---

# References