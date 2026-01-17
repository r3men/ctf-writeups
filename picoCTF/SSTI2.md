# Challenge: SSTI2
**Category:** Web Exploitation
**Difficulty:** Medium
**CTF:** picoCTF 2025

## 📂 Files Provided
- index.html

## 🧠 Approach / Thought Process
- This challenge was a Part II to the previous SSTI challenge (SSTI1). I assumed it would be utilizing a similar exploit to retrieve the flag.
- One of the hints provided regarded blacklisting characters in an attempt to sanitize input. (This meant that I would somehow need to use a different payload/input to extract the flag compared to the prior challenge.)
- I tried the command I used for the previous challenge: {{config.__class__.__init__.__globals__['os'].popen('ls').read()}}, but the website rejected my attempt.
- I figured out that the blocked characters were the '.' and '_' characters, so I needed to find a different way to call the same command without using the blacklisted characters.
- I encoded the underscores with hex using \x5f, and accessed attributes using attr() rather than the '.'.
- After changing the 'ls' to 'cat flag', I was able to get the website to display the flag on the screen.

## 🛠️ Step-by-Step Solution
1. Open the website after launching an instance of the challenge.
2. Enter this as the input: {{ config|attr('\x5f\x5fclass\x5f\x5f')|attr('\x5f\x5finit\x5f\x5f')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('os')|attr('popen')('ls')|attr('read')() }}
3. Submit the input.

## 🎯 Final Flag
`picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bcf73b04}`

