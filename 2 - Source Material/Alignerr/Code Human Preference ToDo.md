# Claude Hfi setup

# Office hours link video
🔗📝 -> [[Code Human Preference Project - Main Hub and Linked Notes]]

# Pick a Repo
***Repo Name*** icecream
🔗***URL*** https://github.com/gruns/icecream

# Connecting A and B
`tmux attach -t <uuid> <-a or -b>`

# [[Questions to evaluate the models on]]


# Create 1 turn-1 prompt
### 1.t1

- [[task 1t1 chp saves]]
- Currently tabs corrupt terminal layout and hide information, null bytes truncate output silently, invisible Unicode characters prevent debugging, and ANSI escape codes execute unintentionally, making it impossible to debug special characters or parse logs. Make IceCream output strings in a way that it preserves all information by default. Icecream should Show control characters and invisibles explicitly instead of letting them affect terminal layout. Decide carefully whether newlines should render literally or as escaped symbols. ambiguous white spaces like /t should not expand into spaces


### 2.t1

- [[task 2 saves]]

- Currently, ic() only accepts positional arguments, and there is no way to pass call-specific options for custom argumentToString handlers. This makes it difficult to use flexible formatting for complex types like NumPy arrays without reconfiguring IceCream globally. I want to be able to define custom argumentToString handlers that can accept optional keyword arguments, and pass those options directly from an ic() call when needed. It should be possible for a custom formatter to support both concise and verbose output on a per-call basis, without changing global configuration. Avoid introducing unnecessary abstractions or global state changes.


### 2.t1

Currently control characters alter output instead of being visible, backspace removes characters and information is lost, `abc\bX` prints as `abX`, invisible Unicode characters like zero-width space `\u200B`, left/right marks `\u200E`, `\u200F` disappear silently preventing debugging, and bytes or bytearrays with characters like `\n` or `\x00` are printed raw producing real line breaks or invisible truncated content, making it impossible to inspect the actual byte sequences or distinguish between printable and non-printable data. output bytes and byte sequences should preserve all info. IceCream should show control characters and invisible Unicode explicitly without letting them alter layout or disappear. Escape sequences should be clearly visible and unambiguous. Destructive characters like backspace should not modify the output representation. All bytes should be represented in a readable hex or escape notation so their actual values are always clear


## interface password
cc_agentic_coding
