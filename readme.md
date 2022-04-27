# NodeJS port of GodSpeak (AKA GodSays) originally made by Terry A. Davis for TempleOS.
## What is GodSpeak?
The original program made by Terry A. Davis is very simple and is made of the following parts:
* A dictionary made by himself based on his ideas. It is made of 712 strings, some of them words, some of them phrases.
* A source of randomness: /dev/urandom which is a files that allows access to environmental noise to generate pseudorandom bytes. Used in Unix-like Operating Systems.
* An array shuffler: gshuf, a GNU coreutil. Terry decided that the ouput should be of 32 strings.
The original Bash script is as follows:
```
#!/bin/bash
#This prints random words.
echo "$(gshuf -n 32 ./Happy.TXT --random-source=/dev/urandom | tr '\n' ' ')"
```
## What makes this port unique?
* I used crypto.randomBytes as the source of randomness. This method will use your system built-in cryptographically secure pseudorandom bytes generator. If using an UNIX-like system, it will use /dev/urandom. This is consistent with Terry A. Davis ideas.
* It then uses an array shuffler, similar to gshuf
## Instalation:
Clone this repository:
```
git clone https://github.com/dvartic/godsays-godspeak-nodejs.git
```
## Usage:
Simply call the godspeak function without any arguments to return an array of the 32 strings which constitutes the result:
```
godspeak()
```
## See also
* https://templeos.org/
* https://github.com/orhun/godsays (Rust Port)
* https://jcpsimmons.github.io/Godspeak-Generator/ (JavaScript Port)
* https://www.youtube.com/watch?v=UCgoxQCf5Jg (TempleOS | Down the Rabbit Hole)