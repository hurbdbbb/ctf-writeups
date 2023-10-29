# Don't stick me there!

## Problem statement
I woke up after a night out and I'm hurting uh... everywhere... I think I left my phone at one of the bars we were at last night. Thankfully, I was able to see the last photo I took through the cloud.

Can you help me find my phone? I need to know the name of the bar and when the photo was taken.

flagformat: NICC{Bar_Name-HH:MM:SS}

## Solution

1. Download the photo "lastphoto.png" ;
2. To find informations related to the time when the photo was taken, we need to see the metadata of the image ;
3. You can go to this site : https://brandfolder.com/workbench/extract-metadata and drag and drop the image ;
4. You can find a variable called ```DateTimeOriginal``` which has the value ```2023-08-13T03:47:12.000+00:00```. With this, we know that the photo was taken at 03:47:12 in the morning ;
5. You can also find another variable called ```GPSPosition``` which has the value ```40 deg 42' 33.02" N, 73 deg 56' 14.04" W```. Whith this, you can find the address of the bar ;
6. You can go to this site : https://www.gps-coordinates.net/ to find the address of the bar by filling the value of the GPS position found above ;
7. The address found is 282 Scholes Street, New York, NY 11206, United States of America ;
8. By searching this address in google maps we can find that the nearest bar from the address is "The Anchored Inn".

By deduction, the flag is : **NICC{The_Anchored_Inn-03:47:12}**
