# Save Info for later
- git head:
	- 55f11b58a9a1ba49721336aa94679f46e1d61b24
	  
- UUID:
	- 05ec9e84-e69f-48eb-aa6d-409940b57edd
	  
- 
	  

# Prompt

Currently, ic() only accepts positional arguments, and there is no way to pass call-specific options for custom argumentToString handlers. This makes it difficult to use flexible formatting for complex types like NumPy arrays without reconfiguring IceCream globally. I want to be able to define custom argumentToString handlers that can accept optional keyword arguments, and pass those options directly from an ic() call when needed. It should be possible for a custom formatter to support both concise and verbose output on a per-call basis, without changing global configuration. Avoid introducing unnecessary abstractions or global state changes.

