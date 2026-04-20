# Challenge: Space Man
**Category:** Forensics
**Difficulty:** Easy
**CTF:** Jersey CTF 2026

## 📂 Files Provided
- Space_Man.png

## 🧠 Approach / Thought Process
- Seeing that the challenge was forensics, was my first instinct was to use exiftool to check for any hidden metadata.
- Since there was nothing of importance, I used the "file" command in case the image was mislabeled.
- Because the image was not mislabeled, steghide wouldn't work since it doesn't support PNG, and I also noticed that the image contained 4 channels, RGBA. This is atypical for images since they usually only contain 3, RGB.
- I tried to extract any files with binwalk, but this was also unsuccessful.
- The last thing I tried involved LSB (Least-Significant-Bit) steganography.
- I prompted Claude with writing me a Python script that extracts any bit planes that contain potentially readable text, which gave me the flag in an encrypted form.
- I tried using an online Ceasar cipher to decode the text, but no amount of rotations did anything.
- The only other cipher I could think of being relevant would be a Vignere cipher, but I was confused since I did not have any keyword to use.
- The challenge description mentioned "space projects that paved the way to the Moon" (Gemini program) and a "dizzying situation" (Gemini 8's uncontrolled spin). This pointed to gemini as the keyword.
- I used an online Vignere cipher decoder with the keyword and got the decoded flag.

## 🛠️ Step-by-Step Solution
1. Download the image file using "wget".
2. Write a script or prompt an LLM of choice to make a script that extracts bit planes from the image and prints any relevant chunks of text.
3. Write another script or prompt an LLM of choice to make a script that uses relevant keywords from the time period and image to continuously attempt to decode the encrypted flag.

## 🎯 Final Flag
`jctf{we_choose_to_go_to_the_moon}`

