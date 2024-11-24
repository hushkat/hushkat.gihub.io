---
title: "SheetsNLayers"
date: 2024-11-24 01:09:33 +0300
author: [hushkat]
description: P3rf3ctr00t CTF Writeups
image: /assets/images/PerfectRoot/SheetsNLayers/PerfectRootLogo.png
categories: [Misc, PerfectRoot]
tags: [Misc, Easy, PerfectRoot]
---

# SheetsNLayers1
## Instructions
What is flag 1?
We are given a file to download which happened to be a zip file. 
![TaskFile](/assets/images/PerfectRoot/SheetsNLayers/TaskFile.png)
I went ahead to unzip the file and found a `SheetsNlayers.vhdx` file, this is a file format used for virtual hard disks. I then mounted the disk on my host machine to explore it further.
![Flag1 Files](/assets/images/PerfectRoot/SheetsNLayers/Flag1&Files.png)
I noticed that it contained three more files, one which just happens to be our first flag, so on opening it, this is what I found: `=03YkNTNlNzYjZjYmVGMmFWZ4MTO1QWY0AzM0MmNhdjMzsHdwAjc`. Looks like a Base64 encoded string. I decoded this string from `https://www.dcode.fr/base-64-encoding` and noticed that it was in reversed form, giving us the flag: `r00t{327a6c4304ad5938eaf0efb6cc3e53dc}` This has been illustrated below:
![Flag1](/assets/images/PerfectRoot/SheetsNLayers/Flag1.png)

# SheetsNLayers2
## Instructions
What is flag 2?

Now that we found flag 1, its time to further explore the rest of the files and see what we can find. I started by reading the note that was present in the disk we accessed. What I found there was this text: `This next archieve contains more flags. Unfortunately the file looks preety blank to me and i can't seem to get all flags. (flag-2 , flag-3, flag-4) Good luck.` So I immediately tried to access the archive called `moreflags.zip` but I couldnt, since it had a password. It was therefore time to start cracking using `JohnTheRipper` by using the following commands on a unix terminal:
```
zip2john moreflags.zip > moreflags.hash #To extract the archive's hash
#The output:
ver 2.0 moreflags.zip/moreflags/ is not encrypted, or stored with non-handled compression type
ver 2.0 moreflags.zip/moreflags/moreflags.xlsx PKZIP Encr: cmplen=10742, decmplen=15277, crc=BADB9879 ts=B4AB cs=badb type=8
                                                                                                                                                                                                                                            
john --wordlist=/usr/share/wordlists/rockyou.txt moreflags.hash #Cracking the hash with the rockyou wordlist
#The output:
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
No password hashes left to crack (see FAQ)

john moreflags.hash --show #To see the cracked hash
#The output:
moreflags.zip/moreflags/moreflags.xlsx:ne.11.88:moreflags/moreflags.xlsx:moreflags.zip::moreflags.zip

1 password hash cracked, 0 left
```
Notice that we manage to get the password to the archive as shown in the output above: `ne.11.88` I then used this password to access the archive.
