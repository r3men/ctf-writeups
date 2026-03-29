# Challenge: Anti AI, at Least the First Time
**Category:** Crypto & Encoding
**Difficulty:** Medium
**CTF:** Garden State CTF 2026

## 📂 Files Provided
- decode.py

## 🧠 Approach / Thought Process
- Honestly, this was one of the most confusing problems I've ever done in a CTF. Like the problem mentioned, AI was of no use here due to its inability to think very surface level.
- Orginally, I tried using AI to somehow decode the hexademical string because I thought it would decode into the required key phrase.
- I tried things like pasting the hex directly into the keyphrase and keeping the ciphertext_hex the same, but to no success.
- Eventually, I stopped using AI assuming that the way to solve the challenge was easier than anticipated.
- Lastly, I realized I had to use all that they gave me, including the string given above the ciphertext hex.
- I thought I was right because that would be something AI would most likely not pick up on, due to it interpreting the hex too literally, as a possible hash of some sorts.
- Realizing this was the correct solution, I was then able to retrieve my flag after slightly modifying the program to use the string given as my key_phrase.

## 🛠️ Step-by-Step Solution
1. Use nano or any file editing software to edit the contents of the given file.
2. Paste the given hexademical string where it says "HEX_CODE_HERE".
3. Paste the key phrase "ChatGPT will not work for this challenge:" where it says "You will never find it".
4. Save the edited program.
5. Run the program using python3 decode.py.

## 🎯 Final Flag
`cyber{right_in_front}`
