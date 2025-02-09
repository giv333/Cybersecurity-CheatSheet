# Password Cracking - John the Ripper

## 🔑 Crack a hashed password
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hashfile

🔍 Show cracked passwords
john --show hashfile


🔎 Identify the hash type
john --test --format=raw-md5

🔐 Crack a ZIP password
john --wordlist=/usr/share/wordlists/rockyou.txt --format=pkzip hashfile


