# Intro-To-John-The-Ripper

John the ripper is a hash cracking tool, same as hashcat. John The Ripper is very similar to hashcat, however one of the key differences is that hashcat cracks mainly using GPU's with a side of CPU while john uses CPU with a side of GPU.

So, depending on your hardware, one or the other might fit your needs better. 

But for now this is going to be a basic rundown of john the ripper. 


## How to install john the ripper. 

I will be going over how to install this on linux, for those of you using kali linux, it should already be installed. 

first run: 
```
sudo apt-get install john
```
or if for some reason that doesnt work. You can use snap but I reccomend using the above
```
sudo snap install john-the-ripper
```

To verify if its installed, just run
```
john
```


## Basic Functionalities

### The most basic usage of john is a dictionary attack, this attack can be used in a single mode or multiple hash mode. 

```
john --wordlist=<wordlist.txt> hashfile
```
All you have to specity the wordlist and hashfile. (NOTE: you may have to specify the path to your wordlist and hashfile)

<br>

### The next basic but useful cracking mode to know is the rules mode.
```
john --wordlist=<wordlist.txt> --rules:<rulename> hashfile
```
All you have to do here is specify the wordlist, hashfile, and rulename you want to use.  (NOTE: you may have to specify the path to your wordlist and hashfile)

<br>

### Other useful basic options to tack onto your john command

```
john --format=<Hash name>
```
Spcifies the hash type, if not added It should auto detect but if it cant, specify. 

```
john --show
```
shows the cracked hashes.
