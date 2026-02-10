# Challenge: rsa_oracle
**Category:** Cryptography
**Difficulty:** Medium
**CTF:** picoCTF 2024

## 📂 Files Provided
- secret.enc
- password.enc

## 🧠 Approach / Thought Process
- The hints given edged me towards using a chosen plaintext attack in order to decrypt the password used to encrypt the flag.
- I saw that the program given was an oracle that had the ability to both decrypt and encrypt. I would most likely have to manipulate the oracle into helping me decrypt the encrypted password, using some sort of RSA exploit.
- I realized that RSA has a multiplicative property where (E(m1) % n) * (E(m2) % n) == E(m1 * m2) % n. This means I can encrypt my own plaintext, get the ciphertext, multiply that ciphertext by the ciphertext of the password, and then from there the oracle will decrypt (reversing encryption), leaving me with the new plaintext which is equivalent to my old plaintext multiplied by the original password plaintext.  

## 🛠️ Step-by-Step Solution
1. 

## 🎯 Final Flag
`picoCTF{my_first_heap_overflow_c3935a08}`
