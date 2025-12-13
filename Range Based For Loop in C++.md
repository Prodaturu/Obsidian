**Created:** *<span class ="color-green">13.12.25, 04:55</span>*
**Created:** 10.12.25, 09:25

**Note Type:** #atomic 

**Hashtags:**
- #cpp 
- #controlflow 
- #loops 

**Topic Tags:**
- #forloops
- #iteration 
- #counters

**Links / Tags:** 
- **Relevance Links:**
    - Loops in C++             %% parent %%
    - [[while loops in C++]]

- **Topic Links:**
    - [[Range Based For Loop in C++]]

---

# 'for' loops in C++

> part of C++ loop mechanisms

a `for` loop repeats code using a clear **start → check → update** pattern.

---

## basic 'for' loop

```cpp
for (initialisation; condition; perLoopUpdate)
{
    // body
}
```

**Translates to:**
- Run *initialisation* once at the start of the loop
- check the condition
- if true $\rightarrow$ run body
- then do the update
- repeat until condition falls (checked at the start of each iteration)

#### Basic Example
