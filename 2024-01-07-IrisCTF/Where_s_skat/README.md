# Where's skat?

## Problem statement

While traveling over the holidays, I was doing some casual wardriving (as I often do). Can you use my capture to find where I went?

Note: the flag is ```irisctf{the_location}```, where ```the_location``` is the full name of my destination location, not the street address. For example, ```irisctf{Washington_Monument}```. Note that the flag is not case sensitive.

The archive given with the challenge is the following: ```wheres-skat.tar.gz```.

Hint: If you're relying on Google Maps to get location names, be careful that it doesn't get lost in translation (for the non-Americans).

## Solution

We used Wireshark to read all of the network packets. After some research on the pcap file, we found a couple of indices by analysing the SSID of each packets : Traxx Restaurant POS, Amtrak_WiFi.

The Traxx Restaurant is located at the Union Station in Los Angeles. Near the Restaurant, we found Amtrak Union Station. By deduction, the location is Los Angeles Union Station.

The flag is: **irisctf{los_angeles_union_station}**