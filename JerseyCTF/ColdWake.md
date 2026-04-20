# Challenge: Cold Wake
**Category:** Forensics
**Difficulty:** Medium
**CTF:** Jersey CTF 2026

## 📂 Files Provided
- 01-cold-wake.zip

## 🧠 Approach / Thought Process
- Knowing the challenge was under "Forensics", I assumed we would be dealing with some form of steganography.
- First, I tried using exiftool for all three tape JPGs. From this, I retrieved the first numerical sequence.
- I did not see anything useful for the metadata for the other two tapes, so I thought about if I would have to extract a file of some sorts from one of the images.
- I tried using binwalk to extract any useful data or files but this was to no success.
- Since there was no password provided for steghide extraction, I thought about somehow brute forcing the password.
- Using stegseek, I bruteforced the password (the same one) for each image file using rockyou.txt.
- I was able to view the hidden payloads for both tape files.
- I tried using "cat" for both files but it looked like a bunch of junk.
- Because of this, I used the "file" command to see what kind of payload I was dealing with.
- I realized it extracted an image file, as well as an MP3 video.
- Viewing both using "xdg-open" and "mpg123" respectively, I was able to retrieve the last two segments of the flag.

## 🛠️ Step-by-Step Solution
1. Download provided ZIP file.
2. Use "unzip" to unzip the ZIP file.
3. Use "exiftool" on Tape1.jpg. Save the flag segment.
4. Use the command: "stegseek [image_name] /usr/share/wordlists/rockyou.txt" for both image files. (PS: You must have the wordlist already downloaded onto your VM)
5. Use the command "xdg-open" to open the image file Tape2.jpg.out. Save the flag segment.
6. Use the command "mpg123" to open the video file Tape3.jpg.out. Save the flag segment.

## 🎯 Final Flag
`jctf{47291-80536-19408}`

