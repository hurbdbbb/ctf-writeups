# sandbox

## Problem statement

I "made" "a" "python" "sandbox" """"
```nc 184.72.87.9 8008```

## Solution

1. Connect to the remote server : ```nc 184.72.87.9 8008```

2. List the content of the files by using this command : ```ls```

3. We can see the following files in the remote server : ```flag.txt```  ```sandbox.py```

4. Run the python sandbox : ```python3 sandbox.py```

5. Display the flag

```
f = open("flag.txt", "r")
print(f.read())
```

The flag is : **flag{did_you_use_ifs_or_python_let_me_know_down_in_the_comments}**
