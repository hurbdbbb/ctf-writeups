# sandbox

## Problem statement

I "made" "a" "python" "sandbox" """"
```nc 184.72.87.9 8008```

## Solution

Connect to the remote server
```nc 184.72.87.9 8008```
List the content of the files
```ls```
We can see the following files in the remote server : ```flag.txt```  ```sandbox.py```
Run the python sandbox
```python3 sandbox.py```
Display the flag
```
f = open("flag.txt", "r")
print(f.read())
```
The flag is : **flag{did_you_use_ifs_or_python_let_me_know_down_in_the_comments}**
