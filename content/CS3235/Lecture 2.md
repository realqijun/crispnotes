## Spatial Memory Error
### Format String Vulnerability
 - Format string - used to provide flexibility during runtime for variadic number of arguments.
 - x86 (32-bit) vs x64(64-bit) - x64 has a few more registers above the return value on stack, arguments are a bit higher.
 - Don't do printf on the input string, use printf("%s", buf) instead.

### Integer overflow
 - Char(-128 - 127) and unsigned char(0-255) represent different range of numbers.
 - Hardware doesn't complain because it still works
 - Takeaway - Hardware doesn't provide protection

### Exploits
 - Code injection - use shell code payload, pad with nops(nop sled) if don't know stack size, overwrite previous function's return address with buffer start.
	 - If there is a check for that payload, conduct code reuse - overflow buffer to execv that is already in memory, and arguments expected on stack.
 - Heap overflow - overwrite heap memory. Allocated chunk list have prev and next at the start of it. Overwriting a chunk overwrites next chunk's pointers.
 - Heartbleed - bug on openssl, reads out of bound 
