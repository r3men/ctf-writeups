# Challenge: Cup O' Joe
**Category:** Binary Exploitation
**Difficulty:** Medium
**CTF:** Garden State CTF 2026

## 📂 Files Provided
- mystery (raw hexdump)

## 🧠 Approach / Thought Process
- I saw that the hexdump began with "cafebabe" indicating the file was a Java .class file.
- Knowing AI could do it faster, I utilized Claude and prompted the AI to take the hexdump and convert the hex to binary.
- The AI was then able to parse the class file structure in Python, revealing the different method signatures and source file name.
- I then asked Claude to decompile the main method code, to get an understanding of what was being done in the .class file.
- Realizing that I needed a password for the XOR cipher, I looked back at the challenge for the password. In doing so, I conducted some research to realize it was a reference to the classic IRC hunter2 meme. I assumed the password was hunter2 as a result.
- Applying the password to the XOR cipher, I was able to successfully retrieve the flag after decoding the hardcoded byte array using a Python script.

## 🛠️ Step-by-Step Solution
1. Manually convert the hexdump into binary or use an AI to do it faster.
2. Decompile the bytecode or have the AI do it instead.
3. Use the challenge information (the meme), to get the password: hunter2.
4. Write a Python program or have AI write one that decodes the hardcoded key array by using the recovered password.

## 🎯 Final Flag
`cyber{no_decaf_here}`
