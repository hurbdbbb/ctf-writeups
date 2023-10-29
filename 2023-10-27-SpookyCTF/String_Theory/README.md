# String Theory

## Problem statement
I recieved this very weird email that only contained a file called "openme", it looks like an executable.

Can you see if there is anything weird in this file?

Hint : I saw that Ghidra is a good tool for looking through executables.

## Solution

1. Open the binary "openme" in [Ghidra](https://ghidra-sre.org/) and analyse the file by Ghidra ;
2. The flag is in the ```.rodata``` section of the code ;

The flag is : **NICC{leaky_data_huh}**
