**Created:** *<span class ="color-green">26.12.25, 06:17</span>*

**Note Type:**

**Hashtags:**
- **Relevance Tags:**
	- 
- **Topic Tags:**
	- 

**Links / Tags:** 
- **Relevance Links:**
	- 
- **Topic Links:**
	- 

---

# CPP 00

> Notes for concepts encountered or learned for the first time during CPP00

- may not include everything
- more like rough notes for concept understanding

## New Concepts used in *cpp00 ex00*
### Why we need casting with `std::toupper`

#### Why does *str::toupper* even cause issues
```cpp
std::cout << std::toupper(str[i])
```

- This would throw an error, because `std::toupper` doesn't return `char`
	- It takes an `int`
	- returns an `int`
- Signature of `std::toupper` is:
```cpp
int  std::toupper(int c);
```
- This means we need to give an `int` and not a `char` to `std::toupper`

#### What happens to `char` when passed to `toupper`
- `char` is promoted to an `int` 
- If `char` is **signed** (common)
- values above 127 can **negative**
- But, std::toupper expects values representable as `unsigned char` 
	- Which would be in the `int` range of `0` - `255`
- when `char` is promoted to `int`
	- `char` could get values out of the required range when its passed to `std::toupper`

#### Why this breaks `std::toupper`
- If a **negative** value is passed (**not eof**):
	- behaviour is undefined
	- function may
		- crash
		- read invalid memory
		- return wrong result
- This is dangerous because:
	- The bug depends on input
	- It may occur only on some systems
	- very hard to debug this issue

#### Why Casting fixes it
```cpp
static_cast<unsigned char>(ch)
```
- This forces:
	- values into range `0` - `255`
	- no negative numbers
	- `toupper` behaves correctly



# Internal References



# External References
