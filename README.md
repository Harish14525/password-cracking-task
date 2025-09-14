# Password Cracking Task – Cyber Security Internship

This repository contains the completed work for Task 2 of the Cyber Security Internship. The task focused on cracking weak passwords using **Hashcat** and **John the Ripper** tools in Kali Linux.

## ✅ Tools Used
Operating System: Kali Linux
Password Cracking Tools:
  - Hashcat v6.2.6 
  - John the Ripper
Wordlists / Dictionaries:
  - rockyou.txt
  - Custom dictionary (`small.txt`)

## ✅ Objective
The objective of this task was to learn how weak passwords are vulnerable to dictionary and brute-force attacks, and to understand how attackers can exploit such weaknesses. We also explored how to defend against these types of attacks.

---

## ✅ Files Included

| File                 | Description                                  |
|----------------------|----------------------------------------------|
| `small.txt`          | A small dictionary containing weak passwords |
| `hashes.txt`         | MD5 hashes cracked using Hashcat             |
| `hashcat_simple.txt` | Cracked output from Hashcat (for reference)  |
| `hash.txt`           | NetNTLMv2 hash cracked using John the Ripper |
| `hash1.txt`          | Second NetNTLMv2 hash cracked using John     |
| `README.md`          | Documentation file explaining the task       |
| `screenshots/`       | Folder containing screenshots of results     |

---

## ✅ Cracked Passwords

### Hashcat (MD5 hashes cracked)

```text
482c811da5d5b4bc6d497ffa98491e38:password123
0d107d09f5bbe40cade3de5c71e9e9b7:letmein
e10adc3949ba59abbe56e057f20f883e:123456


#John the Ripper (NetNTLMv2 hashes cracked)

Administrator::badminton
Admin::123456
```
## ✅ Commands Used
```text
hashcat -m 0 -O hashes.txt small.txt
hashcat --show -m 0 hashes.txt

john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
john --show --format=netntlmv2 hash.txt

john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt
john --show --format=netntlmv2 hash1.txt
```
## ✅ Screenshots

Screenshots showing successful password cracks using both Hashcat and John the Ripper are available in the screenshots/ folder.


## ✅ Learnings
```text

 1 Password Security:
    1. Weak passwords are easily cracked using small or commonly available dictionaries.

2 Hash Vulnerabilities:
    1. MD5 is fast and therefore vulnerable to brute-force attacks.
    2. NetNTLMv2 is more secure but still weak against dictionary attacks when passwords are simple.

3 Tools Knowledge:
    1. Hashcat is GPU-accelerated and ideal for high-speed hash cracking.
    2. John the Ripper is versatile and supports multiple hash formats.

4 Defense Mechanisms:
    1. Use strong, complex passwords with a combination of letters, numbers, and symbols.
    2. Implement password salts to prevent precomputed attacks.
    3. Enforce multi-factor authentication to reduce reliance on passwords.

5 Practical Skills Gained:
    1. Hash identification and cracking.
    2. Using custom and large dictionaries for attacks.
    3. Comparing performance and output of different cracking tools.
```


Author: Harish Babu
