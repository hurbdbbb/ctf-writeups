# Insecure Protocols

## Problem statement
I just spun up my first website with a login page and everything! My friend tells me my page isn't secure and I'm not sure why.

## Solution
1. Open insecure.pcapng in [Wireshark](https://www.wireshark.org/) ;
2. Filter by ```http``` protocols ;
3. There is a ```POST``` request to a page called ```/userinfo.php``` ;
4. By looking at the data in this request we can find the flag.

The flag is : **NICC{h77p_15_1n53cur3}** 
