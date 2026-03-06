# Challenge: Nothing to "C" Here
**Category:** Networking
**Difficulty:** Medium
**CTF:** Garden State CTF 2026

## 📂 Files Provided
- Analysis.pcap

## 🧠 Approach / Thought Process
- I saw that I was working with a .pcap file, meaning I would most likely need to use Wireshark for this challenge.
- Upon conducting initial examination of the file using the query: "dns", I was able to see a list of websites that the user was attempting to access. This is because DNS handles the translations of URLs to IP addresses.
- I noticed a suspicious looking website, and used the URL to perform an nslookup, assuming that the flag was somehow embedded within that website.
- I retrieved the flag after running a command in my terminal that revealed the text records.

## 🛠️ Step-by-Step Solution
1. Use a Virtual Machine of choice and open the packet file in Wireshark.
2. Locate the suspicious website, chsociety.org
3. Use the command nslookup -type=txt chsociety.org to retrieve the flag!

## 🎯 Final Flag
`cyber{always_dns}`
