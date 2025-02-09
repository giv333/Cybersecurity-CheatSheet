# Privilege Escalation Cheat Sheet

## 🔴 Linux Privilege Escalation
```bash
# Check for sudo privileges
sudo -l

# Find files with SUID permissions
find / -perm -4000 -type f 2>/dev/null

# Check kernel version
uname -a

# Find writable directories
find / -type d -writable 2>/dev/null

# Search for .bash_history
cat ~/.bash_history

🔵 Windows Privilege Escalation
powershell

# Check for system privileges
whoami /priv

# List installed programs
wmic product get name,version

# Look for misconfigurations
accesschk.exe -uwcqv "Everyone" *

# Find stored credentials
cmdkey /list
