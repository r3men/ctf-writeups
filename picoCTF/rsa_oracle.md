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
- I then divided out my old plaintext leaving me with just the integer password plaintext. Converting from hex to bytes yields the password needed.
- I then used the openssl command to decrypt the secret.enc file using the decrypted password.

## 🛠️ Step-by-Step Solution
1. Download both given files.
2. Use oracle to encrypt two plaintexts, use gcd() function to retrieve n, the modulus.
3. Generate the final ciphertext for the oracle to decrypt which is represented by multiplying one of your original ciphertexts, and the password ciphertext, then modding by n.
4. Give the oracle your new ciphertext to decrypt.
5. Divide out your original plaintext that you used to yield the plaintext of the password.
6. Convert password from hex to bytes.
7. Use the command: openssl enc -d -aes-256-cbc -in secret.enc -out decrypted.txt -k "password" to retrieve your flag!

## 🎯 Final Flag
`picoCTF{su((3ss_(r@ck1ng_r3@_da099d93}`
