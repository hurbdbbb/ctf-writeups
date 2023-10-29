# What have we found here...

## Problem statement
As the sun dipped below the horizon, casting long shadows across the barren landscape, I stood alone at the edge of the world. The map had brought me here, to this remote and desolate place, in pursuit of a mystery that had captivated the world's greatest minds.

A cryptic message had been found on the ground, a message from the cosmos itself, or so it seemed. It hinted at the existence of extraterrestrial life, hidden within the depths of space. The message, a series of seemingly random characters, held secrets that could change everything we knew about the universe.

My task was to decipher it, to unlock its hidden meaning. The characters appeared to be encoded in a complex language, something that I cannot seem to figure out. The key to understanding lay within those symbols, like a cosmic puzzle waiting to be solved.

As I gazed up at the starry night sky, seeing the Leo Minor constellation in the sky, I knew that the fate of humanity rested on my ability to decode this enigmatic message, to uncover the truth hidden within the stars.

Hint : What rank is the Leo Minor constellation...

## Solution

1. Download "found_notes.txt" ;
2. When opening found_notes.txt we can see a large sequence of random characters. The message is obviously encrypted ;
3. According to the hint, we found on internet that the rank of the Leo Minor constellation was 64 ;
4. We can conclude that the message could be encrypted using a base64 encoding scheme ;
5. By searching on internet for a decoder, you can found a base64 decoder like this : https://www.base64decode.org/ ;
6. add the file "found_notes.txt" and click on "decode" ;
7. After that, download the decoded file. This is a jpeg file containing the flag.

![decoded-20231029085442](https://github.com/Pink-Balloon-Eternal/ctf-writeups/assets/78924080/8fa519f6-8fd9-4c9f-9731-11057923be10)

Flag : **NICC{just_chillin}**
