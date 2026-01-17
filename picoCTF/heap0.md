# Challenge: heap 0
**Category:** Binary Exploitation
**Difficulty:** Easy
**CTF:** picoCTF 2024

## 📂 Files Provided
- chall.c

## 🧠 Approach / Thought Process
- One of the hints given were taking control of one of the variables that is not safe_var and to utilize its distance from safe_var.
- I opened the source code for the challenge and saw that when the program was allocating the two heap buffers, it was using malloc(5). This means it was only allocating 5 bytes, revealing the vulnerability of heap buffer overflow.
- After converting the two heap addresses to decimal, I saw that they had 32 bytes of heap padding. This means that any input for the other heap buffer that surpasses 33 bytes (32 bytes of padding + 1 byte of safe_var) will cause safe_var != "bico").
- Since safe_var is no longer "bico", when "4" is entered to the program, it prints the flag into the terminal.  

## 🛠️ Step-by-Step Solution
1. Run the command: nc tethys.picoctf.net {individual port} (This will allow you to run the program from the source code.)
2. Enter "2"
3. Enter any string longer than 32 characters (will cause heap buffer overflow due to adjacency in memory)
4. Enter "4" to print out the flag string.

## 🎯 Final Flag
`picoCTF{my_first_heap_overflow_c3935a08}`
