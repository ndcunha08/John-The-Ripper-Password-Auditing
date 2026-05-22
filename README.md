# John-The-Ripper-Password-Auditing
This project demonstrates:  Understanding of weak password risks, Knowledge of Linux authentication, Hash cracking concepts, Password auditing, Real-world security testing methodology

# John the Ripper Password Auditing Lab

## Overview

This project demonstrates the use of John the Ripper for password auditing and security analysis within a Linux environment.

The lab focuses on:
- Dictionary attacks
- Rule-based password cracking
- Linux password hash extraction
- Password security weaknesses
- Real-world password behavior analysis

The objective of this lab was to demonstrate how weak passwords can be identified during authorized security testing.

---

# Tools Used

- Kali Linux
- John the Ripper
- RockYou Wordlist
- Linux Password Hashes

---

# Concepts Demonstrated

- Password auditing
- Dictionary attacks
- Rule-based cracking
- Linux password security
- Password hash analysis
- Wordlist-based attacks

---

# Dictionary Attack Overview

A dictionary attack compares password hashes against known words from a password wordlist.

This lab used the RockYou password dictionary because:
- It contains real-world passwords
- It is widely used in security testing
- It is included in Kali Linux
- It simulates common weak password behavior

---

# Wordlist Used

## RockYou Wordlist

Location:
```bash
/usr/share/wordlists/rockyou.txt.gz
```

Preparation:
```bash
gunzip rockyou.txt.gz
```

---

# Password Hash Extraction

Linux password hashes were extracted using:

```bash
sudo unshadow /etc/passwd /etc/shadow > hashes.txt
```

This combines Linux account and shadow password information into a format readable by John the Ripper.

---

# Dictionary Attack

Basic command used:

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt
```

The password was successfully cracked because it existed directly within the RockYou dictionary.

Verification:

```bash
john --show hashes.txt
```

---

# Rule-Based Cracking

Rule-based attacks simulate real-world password behavior.

Common examples include:
- Adding numbers
- Capitalizing letters
- Adding symbols
- Character substitutions

Examples:
- football → Football
- football → football123
- football → football!
- football → f00tball

---

# Rule-Based Attack Command

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt --rules hashes.txt
```

Rules significantly improve password cracking effectiveness against weak passwords.

---

# Security Lessons Learned

This lab demonstrates:
- Weak passwords are highly vulnerable
- Dictionary words should not be used as passwords
- Password complexity alone is not always sufficient
- Users often follow predictable password patterns
- Strong password policies are critical

---

# Skills Demonstrated

- Linux Security
- Password Auditing
- Security Testing
- Hash Analysis
- Dictionary Attacks
- Rule-Based Cracking
- Command-Line Security Tools

---

# Disclaimer

This project was performed in a controlled lab environment for educational and authorized security testing purposes only.

---

# Author

Nicholas Dcunha
