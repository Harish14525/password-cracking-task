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
| `hash.txt`           | NetNTLMv2 hash cracked using John the Ripper |
| `hash1.txt`          | Second NetNTLMv2 hash cracked using John     |
| `md5.txt`            | MD5 hash cracked using brute-force           |
| `sha1.txt`           | SHA1 hash cracked using brute-force          |
| `sha256.txt`         | SHA256 hash cracked using brute-force        |
| `README.md`          | Documentation file explaining the task       |
| `screenshots/`       | Folder containing screenshots of results     |

---

## ✅ Dictionary Attack Results

### Hashcat (MD5 hashes cracked)

```text
482c811da5d5b4bc6d497ffa98491e38:password123
0d107d09f5bbe40cade3de5c71e9e9b7:letmein
e10adc3949ba59abbe56e057f20f883e:123456
```

#John the Ripper (NetNTLMv2 hashes cracked)
```text
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

## ✅ Brute-Force Attack Results

### Hashcat (MD5 hashes cracked)
```text
482c811da5d5b4bc6d497ffa98491e38:password123
```
### Hashcat (SHA1 hashes cracked)
```text
b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3:letmein
```
### Hashcat (SHA256 hashes cracked)
```text
8d969eef6ecad3c29a3a629280e686cff8fab7a7f5f5a5a1e0f22f4bfe7f4f4e:123456
```

## ✅ Commands Used
```text
hashcat -m 0 -a 3 md5.txt ?l?l?l?l?l?l?d?d?d
hashcat --show -m 0 md5.txt

hashcat -m 100 -a 3 -O sha1.txt ?l?l?l?l?l?l?l
hashcat --show -m 100 sha1.txt

hashcat -m 1400 -a 3 sha256.txt ?d?d?d?d?d?d
hashcat --show -m 1400 sha256.txt

```


## ✅ Screenshots

Screenshots showing successful password cracks using both Hashcat and John the Ripper are available in the screenshots/ folder.


## ✅ Learnings
```text

1. Password Security:
   - Weak passwords are easily cracked using dictionaries and brute-force methods.
   - Password length and complexity greatly affect how fast a hash can be cracked.

2. Hash Vulnerabilities:
   - MD5 is fast and vulnerable to brute-force attacks.
   - SHA1 is stronger but still susceptible to brute-force if the password is simple.
   - SHA256 is secure but weak passwords remain exploitable.

3. Attack Strategies:
   - Dictionary attacks are faster for known weak passwords.
   - Brute-force attacks explore all possible combinations but take longer unless constrained.

4. Tools Knowledge:
   - Hashcat’s optimized kernels improve performance.
   - John the Ripper is versatile and supports multiple hash formats.

5. Defensive Measures:
   - Use complex, lengthy passwords combining letters, numbers, and symbols.
   - Implement password salts to protect against precomputed attacks.
   - Enforce multi-factor authentication to strengthen security.

6. Practical Skills Gained:
   - Identifying hash types and selecting attack methods.
   - Configuring masks and optimizing for performance.
   - Comparing dictionary and brute-force approaches.
   - Documenting experiments for reproducibility and learning.

```


Author: Harish Babu
