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

### The next basic cracking mode is the mask mode.
This is essentially a more efficient brute force mode. Instead of just going through every single combination known to man we can specify a format using special characters. Fun Fact, john the ripper supports full syntax for the hashcat masks, so if you are unfamiliar go read my [hashcat](https://github.com/kourtnee/Summer_Work/tree/main/Hashcat) tutorial.

You can also specify your own range of characters in a regex syntax.
```
john --mask=<mask characters> hashfile
```
Regex
```
john --mask=?1?1?1 -1=[A-Z] hashfile
```
the only difference here is that we specify ?1 to run through A-Z. Otherwise if you use hashcat masks it should automatically parse those as what they are. 
