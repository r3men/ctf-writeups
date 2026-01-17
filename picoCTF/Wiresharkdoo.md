# Challenge: Wireshark doo dooo do doo...
**Category:** Forensics
**Difficulty:** Medium 
**CTF:** picoCTF 2021

## 📂 Files Provided
- shark1.pcapng

## 🧠 Approach / Thought Process
- The CTF problem was called mentioned Wireshark, so obviously with the .pcap file and the problem name I asssumed I would be working within that software.
- My first instinct was to try and search for the string "pico" via the Find Packet feature, but I realized it didn't appear so either it was somehow encoded or it wasn't in plainsight.
- Rather than searching for the string directly, I simply searched for a TCP connection between two endpoints and stumbed upon tcp.stream eq 5. I used the Follow TCP Stream to assist me in recovering the flag.

## 🛠️ Step-by-Step Solution
1. Run the command: wireshark shark1.pcapng
2. Use Wireshark's display filter and type: tcp.stream eq 5 (6th TCP Stream)
3. Scroll down within the conversation and locate the string: "Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}"
4. Use a ceasar cipher/ROT13 cipher decoder to decode the string. This gives you the flag.

## 🎯 Final Flag
`picoCTF{p33kab00_1_s33_u_deadbeef}`
