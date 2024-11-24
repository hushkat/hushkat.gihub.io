---
title: "SheetsNlayers"
date: 2024-11-24 01:09:33 +0300
author: [hushkat]
image: /assets/images/PerfectRootLogo.png
categories: [Misc, PerfectRoot]
tags: [Misc, Easy, PerfectRoot]
---

# SheetsNLayers1
## Instructions
What is flag 1?
We are given a file to download which happened to be a zip file. 
![TaskFile](/assets/images/TaskFile.png)
I went ahead to unzip the file and found a `SheetsNlayers.vhdx` file, this is a file format used for virtual hard disks. I then mounted the disk on my host machine to explore it further.
![Flag1 Files](/assets/images/Flag1&Files.png)
I noticed that it contained three more files, one which just happens to be our first flag, so on opening it, this is what I found: `=03YkNTNlNzYjZjYmVGMmFWZ4MTO1QWY0AzM0MmNhdjMzsHdwAjc`. Looks like a Base64 encoded string. I decoded this string from `https://www.dcode.fr/base-64-encoding` and noticed that it was in reversed form, giving us the flag: `r00t{327a6c4304ad5938eaf0efb6cc3e53dc}` This has been illustrated below:
![Flag1](/assets/images/Flag1.png)

# SheetsNLayers2
