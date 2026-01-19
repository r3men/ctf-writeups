# Challenge: Guess My Cheese (Part 1)
**Category:** Cryptography
**Difficulty:** Medium
**CTF:** picoCTF 2025

## 📂 Files Provided
- None

## 🧠 Approach / Thought Process
- The first thing I checked was the hint which mentioned "an affinity for linear equations". I was already suspicious that the problem would involve some type of encryption, so I looked up linear equation ciphers.
- I saw that there was a cipher called the "affine cipher", hence the play on words with affinity.
- Knowing that I had to somehow obtain the a (slope) and b (y-intercept) of the cipher, I used the program within the remote connection to obtain the ciphertext of my chosen plaintext which was Mozzarella.
- Now knowing the ciphertext and plaintext, I could create a python script to reverse engineer for the a and b value of the affine cipher. I used a nested loop to iterate through all possible combinations of a and b values (1 - 26 {number of letters in alphabet}) until I found an a and b value pair that resulted in the ciphertext of my chosen plaintext (mozzarella).
- After obtaining the a and b values of the affine cipher, I used an online affine cipher decoder with the given ciphertext to decrypt it and retrieve the plaintext. 

## 🛠️ Step-by-Step Solution
1. Remotely connect to the running program using netcat.
2. Ask to encrypt a specific plaintext (your choice), and then store the plaintext and corresponding ciphertext.
3. Write a script that goes through all combinations of slopes and y-intercepts for the affine cipher until you find one that when applied to the plaintext of your choice, results in the ciphertext given.
4. Retrieve the slope and y-intercept and use an affine cipher decrypter to retrieve the original plaintext via the initial ciphertext given.

## 🎯 Final Flag
`picoCTF{ChEeSyf4bc3c02}`


