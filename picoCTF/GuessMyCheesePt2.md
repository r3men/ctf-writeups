# Challenge: Guess My Cheese (Part 2)
**Category:** Cryptography
**Difficulty:** Medium
**CTF:** picoCTF 2025

## 📂 Files Provided
- cheese_list.txt

## 🧠 Approach / Thought Process
- By examining the hints, I realized that the cheese was most likely hashed using the SHA-256 algorithm. In addition to this, a one-byte salt was most likely appended or prepended to the plaintext before hashing. The last hint, mentioning rainbow tables, was ascertaining my suspicions of having to create my own rainbow table (in a way).
- To retrieve the original plaintext, since hashes are not reversible by function, I would have to create my own plaintexts and SHA-256 them myself. With this in mind, I created a Python script that went through every single cheese given in the file, tried adding every combination of two letter hexademical strings to both the beginning and end of the plaintext (most common salting methods), and then compares that hash with a known SHA-256 hex digest.
- Since the program asked for the corresponding salt, I made sure to print out both the plaintext along with its salt upon successfully finding them.

## 🛠️ Step-by-Step Solution
1. Remotely connect to the running program via netcat.
2. Take the given SHA-256 hash.
3. Write a script that iterates through all possiblities of one-byte hex strings and tries prepending and appending the strings to each cheese name within the list of cheeses.
4. Ensure that both the plaintext (original message) is printed along with its corresponding salt, which can then be entered into the program to retrieve the flag.

## 🎯 Final Flag
`picoCTF{cHeEsYab922171}`


