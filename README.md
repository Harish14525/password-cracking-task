# Password Cracking Task – Cyber Security Internship

This repository contains the completed work for Task 2 of the Cyber Security Internship. The task focused on cracking weak passwords using **Hashcat** and **John the Ripper** tools in Kali Linux.

## ✅ Tools Used
- Kali Linux
- Hashcat v6.2.6
- John the Ripper
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

## ✅ Commands Used

hashcat -m 0 -O hashes.txt small.txt
hashcat --show -m 0 hashes.txt

john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
john --show --format=netntlmv2 hash.txt

john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt
john --show --format=netntlmv2 hash1.txt

## ✅ Screenshots

Screenshots showing successful password cracks using both Hashcat and John the Ripper are available in the screenshots/ folder.


## ✅ Learnings

 > Simple MD5 hashes are easily cracked using small dictionaries.

 > NetNTLMv2 hashes can also be vulnerable to dictionary attacks if weak passwords are used.

 > Cracking performance depends on memory allocation and system resources.

 > Using strong, complex passwords and adding salt can significantly enhance password security.

 > Understanding password cracking techniques helps in designing better defense mechanisms.



By Harish Babu
