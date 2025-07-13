# คู่มือเริ่มต้นเรียนรู้ Cybersecurity
## สำหรับผู้เริ่มต้น

### วันที่ 1-7: เตรียมพร้อม
- [ ] ติดตั้ง VirtualBox
- [ ] ดาวน์โหลด Kali Linux ISO
- [ ] สร้าง VM แรก
- [ ] ติดตั้ง Kali Linux
- [ ] ทดสอบ internet connection

### สัปดาห์ที่ 1: Linux Basics
```bash
# คำสั่งพื้นฐานที่ต้องรู้
ls -la          # ดูไฟล์และโฟลเดอร์
cd /path/       # เปลี่ยน directory
pwd             # ดูตำแหน่งปัจจุบัน
cat file.txt    # อ่านไฟล์
grep "text"     # ค้นหาข้อความ
chmod +x file   # เปลี่ยน permission
sudo command    # run as root
```

### สัปดาห์ที่ 2: Network Basics
```bash
# เรียนรู้ network commands
ping google.com
nslookup google.com
ifconfig
netstat -tulpn
arp -a
route -n
```

### สัปดาห์ที่ 3: เริ่มต้น Nmap
```bash
# เริ่มจาก command พื้นฐาน
nmap 192.168.1.1              # basic scan
nmap -sn 192.168.1.0/24       # ping sweep
nmap -sS -sV 192.168.1.1      # service version scan
nmap -p 80,443 192.168.1.1    # specific ports
```

### สัปดาห์ที่ 4: Web Application Basics
- ติดตั้ง DVWA
- เรียนรู้ SQL Injection basics
- ทดลองใช้ Burp Suite
- ทำความเข้าใจ HTTP/HTTPS

## แหล่งเรียนรู้ฟรี

### YouTube Playlists
1. **NetworkChuck** - IT Fundamentals
2. **Professor Messer** - CompTIA Security+
3. **Cybrary** - Ethical Hacking
4. **The Cyber Mentor** - Practical Ethical Hacking

### เว็บไซต์ฟรี
1. **Cybrary.it** - Free Cybersecurity Training
2. **SANS Cyber Aces** - Tutorials
3. **OverTheWire** - Command Line Challenges
4. **PicoCTF** - Beginner CTF

### Books (ภาษาอังกฤษ)
1. **"The Basics of Hacking and Penetration Testing"** - Patrick Engebretson
2. **"Penetration Testing: A Hands-On Introduction"** - Georgia Weidman
3. **"The Web Application Hacker's Handbook"** - Dafydd Stuttard

## การฝึกปฏิบัติ

### เดือนที่ 1-2: TryHackMe
- Complete "Pre Security" path
- Try "Introduction to Cyber Security"
- Practice with "Complete Beginner"

### เดือนที่ 3-4: HackTheBox
- สมัครสมาชิก (มี tier ฟรี)
- เริ่มจาก retired easy machines
- ดู writeup หลังจากทำเสร็จ

### เดือนที่ 5-6: VulnHub
- ดาวน์โหลด vulnerable VMs
- ฝึกปฏิบัติใน local environment
- เขียน writeup ของตัวเอง

## เป้าหมายแต่ละเดือน

### เดือนที่ 1: พื้นฐาน
- [ ] ใช้ Linux command line ได้
- [ ] เข้าใจ network basics
- [ ] ติดตั้ง lab environment ได้

### เดือนที่ 2: Tools
- [ ] ใช้ Nmap ได้
- [ ] เข้าใจ Burp Suite basics
- [ ] ใช้ Metasploit ได้

### เดือนที่ 3: Web App Testing
- [ ] ทำ SQL Injection ได้
- [ ] เข้าใจ XSS
- [ ] ใช้ OWASP ZAP ได้

### เดือนที่ 4: System Hacking
- [ ] ทำ privilege escalation
- [ ] เข้าใจ buffer overflow basics
- [ ] ใช้ exploit frameworks

### เดือนที่ 5: Scripting
- [ ] เขียน Python script พื้นฐาน
- [ ] เขียน Bash script
- [ ] Automate scanning tasks

### เดือนที่ 6: Advanced
- [ ] ทำ CTF challenges
- [ ] เขียน exploit code
- [ ] เตรียมตัวสอบ certification

## Certification Path

### Beginner Level
1. **CompTIA Security+** (ราคา ~$400)
   - Foundation knowledge
   - Industry recognized
   - Good for career start

### Intermediate Level
2. **CEH (Certified Ethical Hacker)** (ราคา ~$1,000)
   - Practical skills
   - Hands-on experience
   - Industry standard

### Advanced Level
3. **OSCP (Offensive Security Certified Professional)** (ราคา ~$1,500)
   - Practical exam
   - Highly respected
   - Real-world skills

## Resources สำหรับเรียนรู้

### Free Resources
```
TryHackMe        - https://tryhackme.com/
HackTheBox       - https://www.hackthebox.com/
VulnHub          - https://www.vulnhub.com/
OverTheWire      - https://overthewire.org/
Cybrary          - https://www.cybrary.it/
```

### Paid Resources
```
Pentester Academy - https://www.pentesteracademy.com/
Pluralsight      - https://www.pluralsight.com/
Udemy            - https://www.udemy.com/
Linux Academy    - https://linuxacademy.com/
```

### Tools Repository
```
Kali Linux       - https://www.kali.org/
Parrot Security  - https://www.parrotsec.org/
BlackArch        - https://blackarch.org/
Metasploit       - https://www.metasploit.com/
```

## การสร้าง Portfolio

### GitHub Projects
1. **Vulnerability Scanners**
2. **Exploit Scripts**
3. **CTF Writeups**
4. **Security Tools**

### Blog/Documentation
1. **Technical Writeups**
2. **Tutorial Content**
3. **Security Research**
4. **Tool Reviews**

## Career Paths

### Entry Level Positions
- SOC Analyst
- Security Analyst
- IT Security Specialist
- Cyber Security Intern

### Mid-Level Positions
- Penetration Tester
- Security Consultant
- Incident Response Analyst
- Security Architect

### Senior Level Positions
- Security Engineer
- Security Manager
- Chief Information Security Officer (CISO)
- Security Researcher

---

**สำคัญ:** การเรียนรู้ cybersecurity ต้องใช้เวลา ความอดทน และการฝึกฝนอย่างสม่ำเสมอ เริ่มต้นที่ระดับพื้นฐานและค่อยๆ พัฒนาไปสู่ระดับสูงขึ้น