# Save Info for later
- git head:
	- 55f11b58a9a1ba49721336aa94679f46e1d61b24
	  

# Prompt

currently `ic()` only accepts positional arguments. It does not provide a way to pass additional keyword arguments that could be used by a custom `argumentToString` function. It should be able to define a custom `argumentToString` for special types and pass options to it directly from the `ic()` call