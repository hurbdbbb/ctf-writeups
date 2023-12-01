# Skilift

## Problem statement

You arrive at the base station of a ski lift. Unfortunately for you, the lift is not in operation but you have to reach the next summit somehow. You enter the control room to find a control terminal with the words "Please input your key:"
author: mole99
nc chall.glacierctf.com 13375

download file : top.v

```
module top(
    input [63:0] key,
    output lock
);
  
    reg [63:0] tmp1, tmp2, tmp3, tmp4;

    // Stage 1
    always @(*) begin
        tmp1 = key & 64'hF0F0F0F0F0F0F0F0;
    end
    
    // Stage 2
    always @(*) begin
        tmp2 = tmp1 <<< 5;
    end
    
    // Stage 3
    always @(*) begin
        tmp3 = tmp2 ^ "HACKERS!";
    end

    // Stage 4
    always @(*) begin
        tmp4 = tmp3 - 12345678;
    end

    // I have the feeling "lock" should be 1'b1
    assign lock = tmp4 == 64'h5443474D489DFDD3;

endmodule
```

## Solution

We can see that the key is tranformed at different stage. To find the solution, you have to start at the end result and run backward to retrieve the initial value.

```python
#Skilift

#tmp4 in binary
tmp4 = "5443474D489DFDD3"
tmp4_bin = bin(int(tmp4, 16))
print("tmp4 = ", tmp4_bin)

#tmp3 in binary
tmp3_bin = bin(int(tmp4_bin, 2) + int(bin(12345678), 2))
print("tmp3 = ", tmp3_bin)

#tmp2 in binary
string_hackers = "HACKERS!"
bin_hackers = ''.join(format(ord(i), '08b') for i in string_hackers)
tmp2_bin = bin(int(tmp3_bin, 2) ^ int(bin_hackers, 2))
print("tmp2 = ", tmp2_bin)

#tmp1 in binary
tmp1_bin = bin(int(tmp2_bin, 2) >> 5)
print("tmp1 = ", tmp1_bin)

#key in binary
key = hex(int(tmp1_bin, 2) & int("F0F0F0F0F0F0F0F0", 16))
print("key =", key)
```
