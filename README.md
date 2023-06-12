# Intro-To-John-The-Ripper

John the ripper is a hash cracking tool, same as hashcat. John The Ripper is very similar to hashcat, however one of the key differences is that hashcat cracks mainly using GPU's with a side of CPU while john uses CPU with a side of GPU.

So, depending on your hardware, one or the other might fit your needs better. 

But for now this is going to be a basic rundown of john the ripper. 


## How to install john the ripper. 

I will be going over how to install this on linux, for those of you using kali linux, it should already be installed. 

first run: 
```
git clone "https://github.com/magnumripper/JohnTheRipper.git" && cd JohnTheRipper/src && ./configure && sudo make -s clean && sudo make -sj4 

```
THis is a jumbo installation of john, this command will automatically configure and setup the makefile for you. Personally I put mine in my main user dir.

To verify if its installed, run
```
cd JohnTheRipper/run
./john --help
```

For our case, we are going to ignore basic password cracking, as hashcat is superior. However john being a suite of applications we can use it for other things like extracting hashes from zip files or pdf's.


## Extracting hashes using john

### zip2john
```
cd JohnTheRipper/run
./zip2john <path 2 zip> > <path 2 output file>
```
example
```
./zip2john ~/Downloads/testzip.zip > ~/Downloads/hash.txt
```
This will give you the hash that the password protected zip has. Now its up to you to crack it. Which can be done using john.
```
./john --wordlist=/home/soog/Downloads/rockyou.txt hash.txt
```

![image](https://github.com/JoshuaHartz/Intro-To-John-The-Ripper/assets/102620766/79d20337-01d8-4a50-823e-9daff6fa1314)

you can see the password here is the orange 12345.

You can then use unzip but I like to use 7z instead which you can get with
```
sudo apt-get p7zip-full
```
Now with the password we have we can run this command to open it
```
7z x test.zip
```
then when prompted for the password, use the password we got from cracking the hash. 
