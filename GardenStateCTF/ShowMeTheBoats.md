# Challenge: Show Me the ... Boats?
**Category:** Web Security
**Difficulty:** Medium 
**CTF:** Garden State CTF 2026

## 📂 Files Provided
- boat.png

## 🧠 Approach / Thought Process
- Even though it was in the category of web security, I first used Linux commands like exiftool and steghide to gather some further information about the image, in case the flag was hiden in plainsight. After trying for a little while, I just assumed I would have to find what website this image came from.
- Upon performing a Google Lens search, I was able to see that the image came from bogansbasin.com. After examining the source code using inspect element, I found the flag hidden!

## 🛠️ Step-by-Step Solution
1. Use Google Lens to identify image source.
2. Use DevTools and perform Inspect Element on the website.
3. Retrieve the flag from the source code.

## 🎯 Final Flag
`cyber{bogans_heroes}`
