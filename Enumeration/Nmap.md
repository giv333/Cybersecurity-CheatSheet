# Nmap Cheat Sheet

## 🔍 Basic Scanning
```bash
# Scan a single target
nmap target-ip

# Scan for open ports
nmap -sS -p- target-ip

# Detect OS and service versions
nmap -A target-ip

# Scan a network range
nmap -sP 192.168.1.0/24

# Aggressive scan with scripts
nmap -A -T4 target-ip

