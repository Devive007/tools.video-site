# การตั้งค่าสภาพแวดล้อมการเขียนโปรแกรม
## สำหรับผู้เริ่มต้น

### ขั้นตอนที่ 1: ติดตั้ง Python

#### Windows
```bash
# 1. ไปที่ https://python.org/downloads/
# 2. ดาวน์โหลด Python 3.x (เวอร์ชั่นล่าสุด)
# 3. รันไฟล์ติดตั้ง
# 4. เลือก "Add Python to PATH" (สำคัญ!)
# 5. คลิก "Install Now"

# ทดสอบการติดตั้ง
python --version
pip --version
```

#### macOS
```bash
# วิธีที่ 1: ติดตั้งจาก python.org
# 1. ไปที่ https://python.org/downloads/
# 2. ดาวน์โหลด Python 3.x
# 3. ติดตั้งตามปกติ

# วิธีที่ 2: ใช้ Homebrew
brew install python3

# ทดสอบการติดตั้ง
python3 --version
pip3 --version
```

#### Linux (Ubuntu/Debian)
```bash
# อัปเดตระบบ
sudo apt update
sudo apt upgrade

# ติดตั้ง Python 3
sudo apt install python3 python3-pip

# ติดตั้ง virtual environment
sudo apt install python3-venv

# ทดสอบการติดตั้ง
python3 --version
pip3 --version
```

### ขั้นตอนที่ 2: เลือกและติดตั้ง Text Editor/IDE

#### 1. Visual Studio Code (แนะนำ)
```bash
# ดาวน์โหลดจาก: https://code.visualstudio.com/

# Extension ที่ควรติดตั้ง:
# - Python (Microsoft)
# - Python Docstring Generator
# - Python Indent
# - Code Runner
# - GitLens
# - Bracket Pair Colorizer
```

#### 2. PyCharm Community Edition
```bash
# ดาวน์โหลดจาก: https://www.jetbrains.com/pycharm/download/
# เลือก Community Edition (ฟรี)

# ข้อดี:
# - IDE ที่ทรงพลัง
# - Debugging ที่ดี
# - IntelliSense ที่แม่นยำ
```

#### 3. Sublime Text
```bash
# ดาวน์โหลดจาก: https://www.sublimetext.com/

# Package ที่ควรติดตั้ง:
# - SublimeCodeIntel
# - Python Improved
# - Anaconda
```

#### 4. Atom
```bash
# ดาวน์โหลดจาก: https://atom.io/

# Package ที่ควรติดตั้ง:
# - python-tools
# - autocomplete-python
# - linter-flake8
```

### ขั้นตอนที่ 3: ตั้งค่า Virtual Environment

#### ทำไมต้องใช้ Virtual Environment?
- **แยกโปรเจค** - แต่ละโปรเจคมี libraries ของตัวเอง
- **หลีกเลี่ยงความขัดแย้ง** - ไม่ปะปนกัน
- **จัดการง่าย** - ลบได้ง่าย ไม่กระทบระบบ

#### สร้างและใช้งาน Virtual Environment
```bash
# สร้าง virtual environment
python -m venv myproject_env

# เปิดใช้งาน (Windows)
myproject_env\Scripts\activate

# เปิดใช้งาน (macOS/Linux)
source myproject_env/bin/activate

# ตรวจสอบว่าใช้งานอยู่
which python  # ควรแสดงเส้นทางใน virtual env

# ติดตั้ง packages
pip install requests
pip install beautifulsoup4
pip install pandas

# ดูรายการ packages
pip list

# บันทึกรายการ packages
pip freeze > requirements.txt

# ติดตั้งจาก requirements.txt
pip install -r requirements.txt

# ออกจาก virtual environment
deactivate
```

### ขั้นตอนที่ 4: ตั้งค่า Git

#### ติดตั้ง Git
```bash
# Windows: ดาวน์โหลดจาก https://git-scm.com/
# macOS: brew install git
# Linux: sudo apt install git

# ตั้งค่าเริ่มต้น
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# ตรวจสอบการตั้งค่า
git config --list
```

#### การใช้งาน Git พื้นฐาน
```bash
# เริ่มต้น repository
git init

# เพิ่มไฟล์
git add .
git add filename.py

# Commit
git commit -m "Initial commit"

# ดูสถานะ
git status

# ดูประวัติ
git log

# สร้าง branch
git branch new-feature
git checkout new-feature

# หรือใช้คำสั่งเดียว
git checkout -b new-feature

# Merge branch
git checkout main
git merge new-feature
```

### ขั้นตอนที่ 5: ตั้งค่า GitHub

#### สร้าง GitHub Account
1. ไปที่ https://github.com/
2. สร้างบัญชีใหม่
3. ยืนยันอีเมล

#### เชื่อมต่อ Local Repository กับ GitHub
```bash
# สร้าง repository ใหม่ใน GitHub
# แล้วรันคำสั่งเหล่านี้

# เชื่อมต่อ remote repository
git remote add origin https://github.com/username/repository.git

# Push ครั้งแรก
git push -u origin main

# Push ครั้งต่อไป
git push
```

#### SSH Keys (เพื่อความปลอดภัย)
```bash
# สร้าง SSH key
ssh-keygen -t rsa -b 4096 -C "your.email@example.com"

# แสดง public key
cat ~/.ssh/id_rsa.pub

# Copy และเพิ่มใน GitHub Settings > SSH Keys
```

### ขั้นตอนที่ 6: ตั้งค่า VS Code สำหรับ Python

#### Extensions ที่จำเป็น
```json
{
  "recommendations": [
    "ms-python.python",
    "ms-python.vscode-pylance",
    "ms-toolsai.jupyter",
    "ms-vscode.vscode-json",
    "eamodio.gitlens",
    "ms-python.flake8",
    "ms-python.black-formatter"
  ]
}
```

#### Settings.json
```json
{
  "python.defaultInterpreterPath": "./venv/bin/python",
  "python.terminal.activateEnvironment": true,
  "python.formatting.provider": "black",
  "python.linting.enabled": true,
  "python.linting.pylintEnabled": true,
  "python.linting.flake8Enabled": true,
  "editor.formatOnSave": true,
  "editor.tabSize": 4,
  "editor.insertSpaces": true,
  "files.autoSave": "afterDelay",
  "terminal.integrated.shell.windows": "C:\\Windows\\System32\\cmd.exe"
}
```

### ขั้นตอนที่ 7: ติดตั้ง Useful Libraries

#### Essential Libraries
```bash
# การจัดการข้อมูล
pip install pandas numpy matplotlib seaborn

# Web scraping
pip install requests beautifulsoup4 selenium

# Web framework
pip install flask django

# การทำงานกับ API
pip install requests

# การทำงานกับไฟล์ Excel
pip install openpyxl

# การทำงานกับรูปภาพ
pip install Pillow

# การทำงานกับเวลา
pip install python-dateutil

# การทดสอบ
pip install pytest

# Code formatting
pip install black flake8
```

### ขั้นตอนที่ 8: สร้าง Project Structure

#### โครงสร้างโฟลเดอร์มาตรฐาน
```
my_project/
├── venv/                 # Virtual environment
├── src/                  # Source code
│   ├── __init__.py
│   ├── main.py
│   └── utils.py
├── tests/                # Unit tests
│   ├── __init__.py
│   └── test_main.py
├── docs/                 # Documentation
├── data/                 # Data files
├── .gitignore           # Git ignore file
├── README.md            # Project description
├── requirements.txt     # Dependencies
└── setup.py            # Package setup
```

#### ตัวอย่าง .gitignore
```
# Virtual environment
venv/
env/
ENV/

# Python cache
__pycache__/
*.pyc
*.pyo
*.pyd

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Data
*.csv
*.json
*.xlsx
data/

# Logs
*.log
logs/
```

### ขั้นตอนที่ 9: Debug และ Testing

#### การใช้ Debugger ใน VS Code
```python
# ตั้งค่า launch.json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: Current File",
      "type": "python",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal"
    }
  ]
}
```

#### Unit Testing
```python
# test_example.py
import unittest

def add(a, b):
    return a + b

class TestMath(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
        self.assertEqual(add(-1, 1), 0)
        self.assertEqual(add(0, 0), 0)

if __name__ == '__main__':
    unittest.main()
```

### ขั้นตอนที่ 10: การจัดการโปรเจค

#### Requirements.txt
```txt
# requirements.txt
requests==2.28.1
beautifulsoup4==4.11.1
pandas==1.5.0
numpy==1.23.3
matplotlib==3.5.3
flask==2.2.2
```

#### Setup.py
```python
# setup.py
from setuptools import setup, find_packages

setup(
    name="my_project",
    version="1.0.0",
    packages=find_packages(),
    install_requires=[
        "requests",
        "beautifulsoup4",
        "pandas",
        "numpy",
        "matplotlib",
        "flask"
    ],
    author="Your Name",
    author_email="your.email@example.com",
    description="A simple Python project",
    long_description=open("README.md").read(),
    long_description_content_type="text/markdown",
    url="https://github.com/username/my_project",
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires=">=3.6",
)
```

### เคล็ดลับการใช้งาน

#### 1. Shortcuts ที่ใช้บ่อย (VS Code)
```
Ctrl + `          # เปิด Terminal
Ctrl + Shift + P  # Command Palette
Ctrl + /          # Comment/Uncomment
Ctrl + D          # เลือกคำเดียวกัน
Ctrl + F          # ค้นหา
Ctrl + H          # Find and Replace
F5                # Run Debug
Shift + F5        # Stop Debug
F9                # Toggle Breakpoint
```

#### 2. Python Best Practices
```python
# ใช้ meaningful variable names
user_age = 25  # ดี
ua = 25        # ไม่ดี

# ใช้ comments อย่างมีประโยชน์
# คำนวณภาษี (7%)
tax = price * 0.07

# ใช้ functions แบ่งงาน
def calculate_tax(price, rate=0.07):
    return price * rate

# ใช้ type hints
def greet(name: str) -> str:
    return f"Hello, {name}!"

# ใช้ docstrings
def calculate_area(width: float, height: float) -> float:
    """
    คำนวณพื้นที่สี่เหลี่ยมผืนผ้า
    
    Args:
        width: ความกว้าง
        height: ความสูง
    
    Returns:
        พื้นที่
    """
    return width * height
```

#### 3. การจัดการ Error
```python
# ใช้ try-except
try:
    age = int(input("อายุ: "))
    print(f"คุณอายุ {age} ปี")
except ValueError:
    print("กรุณาใส่ตัวเลข")

# ใช้ logging แทน print
import logging

logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("โปรแกรมเริ่มต้น")
logger.error("เกิดข้อผิดพลาด")
```

### Troubleshooting ปัญหาที่พบบ่อย

#### 1. Python ไม่ทำงาน
```bash
# ตรวจสอบว่าติดตั้งแล้วหรือไม่
python --version

# ตรวจสอบ PATH
echo $PATH

# เพิ่ม Python ใน PATH (Windows)
# เพิ่มใน System Environment Variables
```

#### 2. pip ไม่ทำงาน
```bash
# ติดตั้ง pip ใหม่
python -m ensurepip --upgrade

# อัปเดต pip
python -m pip install --upgrade pip
```

#### 3. Virtual Environment ไม่ทำงาน
```bash
# ลบและสร้างใหม่
rm -rf venv
python -m venv venv

# ใช้งาน
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate     # Windows
```

#### 4. Import Error
```python
# ตรวจสอบว่าติดตั้งแล้วหรือไม่
pip list

# ติดตั้ง package ที่ขาดหาย
pip install package_name

# ตรวจสอบว่าใช้ virtual environment ที่ถูก
which python
```

### Resources เพิ่มเติม

#### เว็บไซต์ที่มีประโยชน์
- **Python.org** - https://python.org/
- **PyPI** - https://pypi.org/
- **Real Python** - https://realpython.com/
- **Python Tutor** - https://pythontutor.com/
- **Stack Overflow** - https://stackoverflow.com/

#### YouTube Channels
- **Corey Schafer** - Python Tutorials
- **Programming with Mosh** - Python for Beginners
- **Tech With Tim** - Python Projects
- **Sentdex** - Python Programming

#### Books
- **"Python Crash Course"** - Eric Matthes
- **"Automate the Boring Stuff with Python"** - Al Sweigart
- **"Fluent Python"** - Luciano Ramalho

---

**สำคัญ:** การตั้งค่าสภาพแวดล้อมที่ดีจะช่วยให้การเขียนโปรแกรมเป็นเรื่องง่ายและสนุกขึ้น ใช้เวลาในการตั้งค่าให้ถูกต้องตั้งแต่เริ่มต้น