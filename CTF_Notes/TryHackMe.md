# TryHackMe Walkthroughs

## 🔹 Enumeration Tips
```bash
# Nmap full port scan
nmap -sC -sV -p- target-ip

# Check for hidden directories
gobuster dir -u http://target-site.com -w /usr/share/wordlists/dirb/common.txt

# Run Nikto for web vulnerabilities
nikto -h http://target-site.com

🔹 Privilege Escalation Techniques
# Check sudo privileges
sudo -l

# Check SUID binaries
find / -perm -4000 -type f 2>/dev/null

🔹 Exploiting Misconfigurations
# Exploiting an unquoted service path (Windows)
wmic service get name,displayname,pathname,startmode | findstr /i "Auto" | findstr /i /v "C:\\Windows"

# Exploit PATH hijacking (Linux)
export PATH=/tmp:$PATH
