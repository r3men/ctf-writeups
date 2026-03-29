# Challenge: Base Access
**Category:** Crypto & Encoding
**Difficulty:** Medium
**CTF:** Garden State CTF 2026

## 📂 Files Provided
- N/A

## 🧠 Approach / Thought Process
- I tried to connect using nc with my school's free Kali Linux machine on USCyberRange but it did not work.
- Instead, I tried to see if there were any other alternatives.
- I stumbled across JSLinux, which provides access to a Linux machine online.
- Upon ncing to the remote program, I realized it limited access to several key commands like cat, less, etc.
- I assumed this meant I would have to try different commands to see which worked and which didn't.
- I realized some basic commands like cd and ls were available, so I used those to figure out what kind of files and directories were located on the machine.
- I found the authentication checker after changing to the .secrets directory.
- I tried different commands that would allow me to view parts of the program until I saw that strings worked.
- I saw that one of the strings given was in Base64 (indicated by the succeeding equal sign at the end), so I tried decoding it online and I got the flag!

## 🛠️ Step-by-Step Solution
1. Use an free online linux machine like the ones on JSLinux.
2. Run the given command: nc 0.cloud.chals.io 18833
3. Run the command cd .secrets (Move into the .secrets directory)
4. Run the command strings auth_check.py (see what strings are in the program)
5. Take Base64 string and use an online decoder or Linux command to decode it.

## 🎯 Final Flag
`ctf{hardcoded_passwords_are_bad}`
