---
title: "SheetsNlayers"
date: 2024-11-22 01:09:33 +0300
author: hushkat
image: /assets/img/Posts/PerfectRootLogo.png
categories: [Misc, PerfectRoot]
tags: [Misc, PerfectRoot]
---

# SheetsNLayers - Flag 1 - misc
## Instructions
What is flag 1?
We are given a file to download which happened to be a zip file. 
![TaskFile](https://gist.github.com/user-attachments/assets/77dee2b5-03b8-4b68-bbfe-1a0ef2ccc762)
I went ahead to unzip the file and found a `SheetsNlayers.vhdx` file, this is a file format used for virtual hard disks. I then mounted the disk on my host machine to explore it further.
![Flag1 Files](https://gist.github.com/user-attachments/assets/6f0f0fe4-b3df-4aa3-9173-dae8164a1567)
I noticed that it contained three more files, one which just happens to be our first flag, so on opening it, this is what I found: `=03YkNTNlNzYjZjYmVGMmFWZ4MTO1QWY0AzM0MmNhdjMzsHdwAjc`. Looks like a Base64 encoded string. I decoded this string from `https://www.dcode.fr/base-64-encoding` and noticed that it was in reversed form, giving us the flag: `r00t{327a6c4304ad5938eaf0efb6cc3e53dc}` This has been illustrated below:
![Flag1](https://gist.github.com/user-attachments/assets/cd50a180-34d7-4a82-b02d-42e27c6a33a1)
