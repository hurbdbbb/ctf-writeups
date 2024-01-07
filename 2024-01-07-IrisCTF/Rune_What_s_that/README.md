# Rune? What's that?

## Problem Statement

Rune? Like the ancient alphabet?

Archive given in the challenge : ```whats-a-rune.tar.gz```

## Solution

The goal is to decrypt the following string contained in the file named "the": ```iÛÛÜÖ×ÚáäÈÑ¥gebªØÔÍãâ£i¥§²ËÅÒÍÈä```

We have a file named ```main.go``` that contain the following code :

```
package main

import (
	"fmt"
	"os"
	"strings"
)

var flag = "irisctf{this_is_not_the_real_flag}"

func init() {
	runed := []string{}
	z := rune(0)

	for _, v := range flag {
		runed = append(runed, string(v+z))
		z = v
	}

	flag = strings.Join(runed, "")
}

func main() {
	file, err := os.OpenFile("the", os.O_RDWR|os.O_CREATE, 0644)
	if err != nil {
		fmt.Println(err)
		return
	}

	defer file.Close()
	if _, err := file.Write([]byte(flag)); err != nil {
		fmt.Println(err)
		return
	}
}
```

We can see that the code above contain the logic to change the value of the flag into another string of characters. In order to retrieve the original value of the flag contained in the file ```the```. We have to reverse engineer the algorithm and doing the opposite.

Here is the python script that retrieve the original value of the flag:

```
with open('the', 'r') as file:
    encoded_flag = file.read().rstrip()
decoded_flag = ""
v = 0
k = 0
while k < len(encoded_flag):
    runed = ord(encoded_flag[k])
    z = runed - v
    v = z
    decoded_flag += chr(v)
    k+=1
print("encoded flag: ", encoded_flag)
print("flag: ", decoded_flag)
```
The output of the program is the following:
```
encoded flag:  iÛÛÜÖ×ÚáäÈÑ¥gebªØÔÍãâ£i¥§²ËÅÒÍÈä
flag:  irisctf{i_r3411y_1ik3_num63r5}Nw[rV
```