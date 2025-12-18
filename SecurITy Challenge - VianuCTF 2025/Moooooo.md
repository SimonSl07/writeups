# Moooooo - writeup
**AUTHOR** - Kirkos (myself) | 
**CATEGORY** - Forensics / OSINT | 
**CHALLENGE FILE** - ReallySussyFile

1. We are given the file named ReallySussyFile. Using exiftool on it reveals to us the comment: "V1ANUF0R3V3R". This is a red herring which can be interpreted as either part of the flag or as a username. 
---
2. By looking at the hex data of the file we can tell that it is a .jpg image with the first 4 bytes changed to 69. If we change those bytes back to the original header (FF D8 FF E0) - I used a [random website](https://hexed.it) I found - and open the image, we see a caption in the down right corner with the word "GH1TAB0SSUR3G3LE".
---
3. The word is pretty obviously a username, which if we look up(using a tool like sherlock) we find a github account with that username.
---
4. In one of the repos (named "Djibooty") there is an issue (named "Out of toilet paper") with an encoded flag: D1ETr0ysGQOJZ18jHmSBIS9GGmNjGmOsGIIQFU0=
---
5. Decoding the found text(ROT13 -> From base 64)  yields the flag: **CTF{I_L0V3_0S1NT_SO00O0_MUCH}**
---
Common wrong paths I saw people take during the competition:
- Believing that the two words "V1ANUF0R3V3R" and "GH1TAB0SSUR3G3LE" form the flag (Something like: CTF{V1ANUF0R3V3R_GH1TAB0SSUR3G3LE})
- Believing that somehow finding the location shown in the image will yield the flag - It's just a random image of some cows :)
- Also because I'm a pain in the ass I had a red herring [here](https://github.com/GH1TAB0SSUR3G3LE/Djibooty/blob/main/the%20booty) which when decoded gave this: CTF{ HA SIKE NO FLAG FOR YOU HEHE YOU WILL NEVER FIND MEEE}
