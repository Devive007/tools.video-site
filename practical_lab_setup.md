# การตั้งค่า Lab สำหรับเรียนรู้ Cybersecurity

## ขั้นตอนการเริ่มต้น

### 1. ติดตั้ง Virtual Machine Software
```bash
# สำหรับ Ubuntu/Debian
sudo apt update
sudo apt install virtualbox virtualbox-ext-pack
sudo apt install vmware-workstation-player

# สำหรับ Windows
# ดาวน์โหลด VirtualBox จาก https://www.virtualbox.org/
# ดาวน์โหลด VMware จาก https://www.vmware.com/
```

### 2. ดาวน์โหลด Operating Systems
- **Kali Linux** (สำหรับ Penetration Testing)
  - https://www.kali.org/get-kali/
  - เลือก Virtual Machine images

- **Metasploitable** (สำหรับฝึกปฏิบัติ)
  - https://sourceforge.net/projects/metasploitable/

- **DVWA** (Damn Vulnerable Web Application)
  - https://github.com/digininja/DVWA

### 3. การตั้งค่าเครือข่าย
```bash
# ใน VirtualBox
# สร้าง Internal Network สำหรับ Lab
# Network Settings -> Adapter 1 -> Internal Network
# Name: CyberLab
```

### 4. เครื่องมือพื้นฐาน (ติดตั้งใน Kali Linux)
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# เครื่องมือ Network Scanning
sudo apt install nmap masscan
sudo apt install netdiscover arp-scan

# เครื่องมือ Web Application Testing
sudo apt install burpsuite
sudo apt install sqlmap
sudo apt install nikto

# เครื่องมือ Exploitation
sudo apt install metasploit-framework
sudo apt install exploitdb
sudo apt install searchsploit

# เครื่องมือ Forensics
sudo apt install autopsy
sudo apt install foremost
sudo apt install binwalk
```

### 5. Python Environment สำหรับ Scripting
```bash
# ติดตั้ง Python tools
pip3 install requests
pip3 install beautifulsoup4
pip3 install scapy
pip3 install pycryptodome
pip3 install paramiko
```

### 6. ตัวอย่างการใช้งาน

#### 6.1 Network Scanning
```bash
# สแกนเครือข่าย
nmap -sn 192.168.1.0/24

# สแกน Port
nmap -sS -sV -O target_ip

# สแกน Vulnerability
nmap --script vuln target_ip
```

#### 6.2 Web Application Testing
```bash
# ใช้ Burp Suite
# 1. เปิด Burp Suite
# 2. ตั้งค่า Browser proxy ไปที่ 127.0.0.1:8080
# 3. Import Burp CA Certificate
# 4. เริ่มสกัดกั้น Traffic

# ใช้ SQLMap
sqlmap -u "http://target.com/page.php?id=1" --dbs
sqlmap -u "http://target.com/page.php?id=1" --dump
```

#### 6.3 System Enumeration
```bash
# Linux Enumeration
cat /etc/passwd
cat /etc/shadow
ps aux
netstat -tulpn
find / -perm -4000 2>/dev/null

# Windows Enumeration
systeminfo
net user
net localgroup administrators
tasklist
netstat -an
```

## Legal Lab Environments

### Online Platforms
1. **TryHackMe** - https://tryhackme.com/
2. **HackTheBox** - https://www.hackthebox.com/
3. **VulnHub** - https://www.vulnhub.com/
4. **OverTheWire** - https://overthewire.org/wargames/

### Downloadable VMs
1. **DVWA** - Web Application Testing
2. **WebGoat** - OWASP Web Security
3. **Metasploitable** - Linux Exploitation
4. **VulnServer** - Windows Buffer Overflow

## การเรียนรู้ Programming

### Python สำหรับ Cybersecurity
```python
# ตัวอย่าง Port Scanner
import socket
import threading

def scan_port(host, port):
    try:
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(1)
        result = sock.connect_ex((host, port))
        if result == 0:
            print(f"Port {port}: Open")
        sock.close()
    except:
        pass

# ใช้งาน
host = "192.168.1.1"
for port in range(1, 1001):
    thread = threading.Thread(target=scan_port, args=(host, port))
    thread.start()
```

### Bash Script สำหรับ Automation
```bash
#!/bin/bash
# ตัวอย่าง Network Discovery Script

echo "Starting network discovery..."
network="192.168.1"

for i in {1..254}; do
    ping -c 1 -W 1 $network.$i &> /dev/null
    if [ $? -eq 0 ]; then
        echo "Host $network.$i is up"
    fi
done
```

## ข้อควรระวัง

### ⚠️ Legal Considerations
- **ใช้เฉพาะใน Lab Environment เท่านั้น**
- **ไม่ทดสอบระบบที่ไม่ได้รับอนุญาต**
- **ปฏิบัติตาม Responsible Disclosure**

### 🔒 Security Best Practices
- **แยก Lab Network จากเครือข่ายหลัก**
- **ใช้ Snapshot ของ VM เป็นประจำ**
- **อัปเดต Tools และ OS เป็นประจำ**
- **เก็บ Log การเรียนรู้ไว้**

---

**หมายเหตุ:** Lab Environment นี้สำหรับการเรียนรู้เท่านั้น ห้ามนำไปใช้ในการโจมตีระบบจริง