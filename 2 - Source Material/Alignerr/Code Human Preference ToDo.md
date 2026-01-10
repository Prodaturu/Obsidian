# Claude Hfi setup

# Office hours link video
🔗📝 -> [[Code Human Preference Project - Main Hub and Linked Notes]]

# Pick a Repo
***Repo Name*** icecream
🔗***URL*** https://github.com/gruns/icecream

# Create 1 turn-1 prompt

Currently tabs corrupt terminal layout and hide information, null bytes truncate output silently, invisible Unicode characters prevent debugging, and ANSI escape codes execute unintentionally, making it impossible to debug special characters or parse logs. Make IceCream output strings in a way that it preserves all information by default. 
Icecream should Show control characters and invisibles explicitly instead of letting them affect terminal layout. Decide carefully whether newlines should render literally or as escaped symbols. ambiguous white spaces like /t should not expand into spaces


1. Control characters alter the output instead of being visible.  
    For instance, \b (backspace) removes characters → abc\bX prints as abX (information lost).
2. Invisible Unicode characters disappear silently.  
    For instance, Zero-width space (\u200B), left/right marks (\u200E, \u200F) are not shown → the user cannot tell they exist.
3. Bytes / bytearray with control characters.  
	For instance, bytes with \n or \x00 are printed raw, producing real line breaks or invisible content



## interface password
cc_agentic_coding
