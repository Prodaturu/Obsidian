**Created:** *<span class ="color-green">22.12.25, 06:11</span>*

**Note Type:** #atomic

**Hashtags:**
- **Relevance Tags:**
	- #cpp
	- #lambdafunctions
	- #oop
- **Topic Tags:**
	- #this
	- #captures
	- #objectlifetime

**Links / Tags:** 
- **Relevance Links:**
	- Lambda Capture Modes in C++
	- Classes in C++
- **Topic Links:**
	- [[Const Member Functions in C++]]

---

# Capturing `this` in C++

> how lambdas access the current object inside member functions.

- `this` is a pointer to the **current object**.
- When a lambda is written inside a member function
- it does **not** automatically have access to the object 
- we must decide **how** to capture it.
---

## Capturing `this` explicitly

```cpp
class counter
{
private:
	int value = 0;
	
public:
	void run()
	{
		auto inc = [this]()
		{
			value++;
		};
		
		inc();
	}
}
```
- `[this]` captures the **pointer** to object
- the lambda works on the **original object**
- any modification affects the real instance
- This is the **classic and most common** form

---
## Lifetime Risk

- Because `[this]`

# Internal References



# External References
