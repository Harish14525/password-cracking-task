# Analysis Report – Password Cracking with Hashcat and John the Ripper

## Objective
The objective of this task was to explore how weak passwords can be compromised through dictionary and brute-force attacks using tools like Hashcat and John the Ripper. The goal was to understand the risks associated with simple passwords and outdated hashing algorithms and learn practical approaches to enhance password security.

## Tools and Environment
1. **Hashcat v6.2.6** – Used to perform dictionary and brute-force attacks on various hash types including MD5, SHA1, and SHA256.
2. **John the Ripper** – Used for validating hash formats and assisting with brute-force and dictionary attacks.
3. **Kali Linux** – The operating system used to execute all cracking tasks.
4. **Wordlists**:
   - `rockyou.txt` – A widely used wordlist containing common passwords.
   - `small.txt` – A custom dictionary with a few sample weak passwords.

## Methodology
1. **Hash Creation**:
   - Created hash files containing MD5, SHA1, and SHA256 hashes for known passwords such as `password123`, `letmein`, and `123456`.
2. **Dictionary Attacks**:
   - Used Hashcat’s dictionary attack mode (`-a 0`) with `rockyou.txt` and `small.txt` to crack weak passwords quickly.
   - Example command:
     ```bash
     hashcat -m 0 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt
     ```
3. **Brute-Force Attacks**:
   - Used Hashcat’s brute-force mode (`-a 3`) with targeted masks to attempt all possible combinations within practical limits.
   - Example commands:
     ```bash
     hashcat -m 100 -a 3 -O sha1.txt ?l?l?l?l?l?l?l
     hashcat -m 1400 -a 3 sha256.txt ?d?d?d?d?d?d
     ```
4. **Verification**:
   - Used `--show` to review cracked passwords.
   - Documented each stage with screenshots.
5. **Comparative Analysis**:
   - Compared the speed and effectiveness of dictionary versus brute-force attacks.
   - Analyzed which hash types were easier or harder to crack based on password complexity and algorithm strength.

## Findings and Observations
1. **Weak Passwords are Easily Cracked**:
   - Passwords like `password123`, `letmein`, and `123456` were cracked within seconds using dictionary attacks.
2. **Hashing Algorithm Matters**:
   - MD5 hashes were the fastest to crack, followed by SHA1, while SHA256 was slower but still vulnerable to simple passwords.
3. **Password Length and Complexity Increase Security**:
   - Passwords longer than 8 characters with mixed characters showed significantly more resistance in brute-force attacks.
4. **Optimized Kernels Improve Performance**:
   - Using `-O` flag in Hashcat enhanced performance during brute-force attempts without compromising accuracy.
5. **Brute-Force Requires Correct Masking**:
   - Incorrect length masks led to exhaustive but ineffective cracking attempts, reinforcing the importance of proper configuration.

## Security Issues Identified
1. **Use of Weak Passwords**:
   - Simple and commonly used passwords are highly susceptible to cracking.
2. **Reliance on Outdated Hashing Algorithms**:
   - MD5 and SHA1 are considered weak and should be avoided for password storage.
3. **Lack of Salting and Iterations**:
   - Absence of additional security measures makes systems prone to dictionary and rainbow table attacks.
4. **Absence of Rate Limiting**:
   - Systems without restrictions on login attempts are vulnerable to brute-force attacks.

## Recommendations
1. **Enforce Strong Password Policies**:
   - Passwords should be complex, including letters (upper and lower case), numbers, and special characters, with a recommended minimum of 12 characters.
2. **Avoid Weak Hashing Algorithms**:
   - Use modern, secure algorithms like bcrypt or Argon2 which incorporate salting and multiple rounds of hashing.
3. **Implement Salting and Iterations**:
   - Add random salts and increase iterations to reduce vulnerability to precomputed attacks.
4. **Apply Account Lockout Mechanisms**:
   - Introduce time delays or lock accounts after multiple failed login attempts to hinder brute-force attacks.
5. **Educate Users**:
   - Conduct training on password hygiene, discouraging reuse and promoting password managers.
6. **Regular Audits and Monitoring**:
   - Continuously monitor for unauthorized access attempts and review password policies for compliance and effectiveness.

## Conclusion
This exercise successfully demonstrated how easily weak passwords can be compromised using popular tools like Hashcat and John the Ripper. It highlighted the critical need for strong passwords, modern hashing algorithms, and layered security defenses. The hands-on experience provided a deeper understanding of password cracking techniques and the importance of implementing robust authentication protocols to safeguard systems from potential threats.

---

**Author**: Harish Babu
