# Challenge: Verify
**Category:** Forensics
**Difficulty:** Easy  

**CTF:** picoCTF 2024

## 📂 Files Provided
- unknown.zip

## 🧠 Approach / Thought Process
- I noticed the file given was a zip, so I assumed in order to retrieve the flag I would first need to unzip the file (also supported through one of the hints given on the website.)
- I identified a common solution to CTFs involving images which typically involves identifying image metadata, extracting a flag from the image itself, or using a hexeditor to edit the raw bytes.

## 🛠️ Step-by-Step Solution
1. Run the command: unzip unknown.zip (This unzips the zip file allowing you to see the JPG image inside.)
2. Run the command: exiftool ukn_reality.jpg (This allows you to see the image metadata.)
3. Use CyberChef or a Base64 decoder to decode the Base64 encoded Attribution URL: cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg== (This is the flag.)

## 🎯 Final Flag
`picoCTF{ME74D47A_HIDD3N_a6df8db8}`
