# การเรียนรู้การเขียนโปรแกรมตั้งแต่ศูนย์
## จากไม่รู้อะไรเลยสู่การเป็นโปรแกรมเมอร์มืออาชีพ

### ทำไมต้องเรียนเขียนโปรแกรม?
- **แก้ปัญหาอัตโนมัติ** - ทำงานซ้ำๆ ให้คอมพิวเตอร์ทำแทน
- **สร้างโปรแกรมของตัวเอง** - เว็บไซต์, แอพ, เกม
- **อาชีพที่ต้องการสูง** - เงินเดือนดี อนาคตมั่นคง
- **ทักษะแห่งอนาคต** - ทุกอุตสาหกรรมต้องการ

---

## ระยะที่ 1: ความเข้าใจพื้นฐาน (สัปดาห์ที่ 1-2)

### คอมพิวเตอร์ทำงานอย่างไร?
```
1. รับข้อมูล (Input) - จากคีย์บอร์ด, เมาส์, ไฟล์
2. ประมวลผล (Process) - คำนวณ, เปรียบเทียบ, ตัดสินใจ
3. แสดงผล (Output) - หน้าจอ, ไฟล์, เสียง
```

### โปรแกรมคืออะไร?
```
โปรแกรม = ชุดคำสั่งที่บอกคอมพิวเตอร์ว่าให้ทำอะไร
เหมือนสูตรอาหาร = ขั้นตอนที่ต้องทำตามลำดับ
```

### ภาษาโปรแกรมคืออะไร?
```
ภาษาที่มนุษย์ใช้สื่อสารกับคอมพิวเตอร์
เหมือนภาษาอังกฤษ แต่มีกฎเกณฑ์เข้มงวดกว่า
```

---

## ระยะที่ 2: เริ่มต้นกับ Python (สัปดาห์ที่ 3-8)

### ทำไมเลือก Python?
- **ง่ายที่สุด** - ใกล้เคียงภาษาอังกฤษ
- **ใช้ได้หลากหลาย** - Web, Data Science, AI
- **Community ใหญ่** - หาความช่วยเหลือง่าย
- **ต้องการสูง** - งานเยอะ

### การติดตั้ง Python
```bash
# Windows
1. ไปที่ python.org
2. ดาวน์โหลด Python 3.x
3. ติดตั้ง (เลือก "Add to PATH")
4. เปิด Command Prompt
5. พิมพ์: python --version

# macOS
brew install python3

# Linux
sudo apt install python3 python3-pip
```

### โปรแกรมแรก - Hello World
```python
print("Hello, World!")
print("สวัสดี ชาวโลก!")
```

**อธิบาย:**
- `print()` = คำสั่งแสดงผล
- `" "` = ข้อความ (String)
- `;` ไม่จำเป็นใน Python

---

## สัปดาห์ที่ 3: ตัวแปร (Variables)

### ตัวแปรคืออะไร?
```python
# ตัวแปร = กล่องใส่ข้อมูล
name = "จอห์น"        # ข้อความ (String)
age = 25             # ตัวเลข (Integer)
height = 1.75        # ทศนิยม (Float)
is_student = True    # จริง/เท็จ (Boolean)

print(name)          # จอห์น
print(age)           # 25
print(height)        # 1.75
print(is_student)    # True
```

### ประเภทของข้อมูล
```python
# String (ข้อความ)
message = "Hello"
message = 'Hello'    # เหมือนกัน

# Integer (จำนวนเต็ม)
score = 100
temperature = -5

# Float (ทศนิยม)
price = 19.99
pi = 3.14159

# Boolean (จริง/เท็จ)
is_open = True
is_closed = False
```

---

## สัปดาห์ที่ 4: การคำนวณ (Operations)

### การคำนวณพื้นฐาน
```python
# การคำนวณ
a = 10
b = 3

print(a + b)    # 13 (บวก)
print(a - b)    # 7  (ลบ)
print(a * b)    # 30 (คูณ)
print(a / b)    # 3.333... (หาร)
print(a // b)   # 3 (หารปัดเศษ)
print(a % b)    # 1 (หารเอาเศษ)
print(a ** b)   # 1000 (ยกกำลัง)
```

### การจัดการข้อความ
```python
first_name = "จอห์น"
last_name = "สมิธ"

# รวมข้อความ
full_name = first_name + " " + last_name
print(full_name)  # จอห์น สมิธ

# ความยาวข้อความ
print(len(full_name))  # 9

# ตัวพิมพ์ใหญ่/เล็ก
print(full_name.upper())  # จอห์น สมิธ
print(full_name.lower())  # จอห์น สมิธ
```

---

## สัปดาห์ที่ 5: การรับข้อมูล (Input)

### รับข้อมูลจากผู้ใช้
```python
# รับข้อมูล
name = input("ชื่อของคุณ: ")
age = input("อายุของคุณ: ")

print("สวัสดี " + name)
print("คุณอายุ " + age + " ปี")
```

### แปลงประเภทข้อมูล
```python
# input() ให้ผลเป็น String เสมอ
age_text = input("อายุ: ")        # "25"
age_number = int(age_text)        # 25

# หรือแปลงเลย
age = int(input("อายุ: "))
height = float(input("ส่วนสูง: "))

# ตัวอย่างโปรแกรม
name = input("ชื่อ: ")
age = int(input("อายุ: "))
next_year = age + 1

print(f"สวัสดี {name}")
print(f"ปีหน้าคุณจะอายุ {next_year} ปี")
```

---

## สัปดาห์ที่ 6: การตัดสินใจ (If-Else)

### การเปรียบเทียบ
```python
a = 10
b = 5

print(a > b)   # True (มากกว่า)
print(a < b)   # False (น้อยกว่า)
print(a == b)  # False (เท่ากับ)
print(a != b)  # True (ไม่เท่ากับ)
print(a >= b)  # True (มากกว่าหรือเท่ากับ)
print(a <= b)  # False (น้อยกว่าหรือเท่ากับ)
```

### If-Else Statement
```python
age = int(input("อายุ: "))

if age >= 18:
    print("คุณเป็นผู้ใหญ่แล้ว")
else:
    print("คุณยังเป็นเด็ก")
```

### If-Elif-Else
```python
score = int(input("คะแนน: "))

if score >= 80:
    print("เกรด A")
elif score >= 70:
    print("เกรด B")
elif score >= 60:
    print("เกรด C")
else:
    print("เกรด F")
```

---

## สัปดาห์ที่ 7: การทำซ้ำ (Loops)

### For Loop
```python
# พิมพ์ 1-10
for i in range(1, 11):
    print(i)

# พิมพ์ข้อความ 5 รอบ
for i in range(5):
    print("สวัสดี")

# วนลูปใน List
fruits = ["แอปเปิล", "กล้วย", "องุ่น"]
for fruit in fruits:
    print(fruit)
```

### While Loop
```python
# นับ 1-10
count = 1
while count <= 10:
    print(count)
    count = count + 1

# รับข้อมูลจนกว่าจะถูก
password = ""
while password != "secret":
    password = input("รหัสผ่าน: ")
    if password != "secret":
        print("ผิด! ลองใหม่")
print("ถูกต้อง!")
```

---

## สัปดาห์ที่ 8: รายการ (Lists)

### List พื้นฐาน
```python
# สร้าง List
numbers = [1, 2, 3, 4, 5]
names = ["จอห์น", "แมรี่", "บ็อบ"]
mixed = [1, "hello", 3.14, True]

# เข้าถึงข้อมูล
print(numbers[0])    # 1 (ตัวแรก)
print(numbers[-1])   # 5 (ตัวสุดท้าย)
print(names[1])      # แมรี่
```

### จัดการ List
```python
fruits = ["แอปเปิล", "กล้วย"]

# เพิ่มข้อมูล
fruits.append("องุ่น")           # ["แอปเปิล", "กล้วย", "องุ่น"]
fruits.insert(1, "มะม่วง")       # ["แอปเปิล", "มะม่วง", "กล้วย", "องุ่น"]

# ลบข้อมูล
fruits.remove("กล้วย")          # ลบ "กล้วย"
last_fruit = fruits.pop()      # ลบตัวสุดท้าย

# ความยาว
print(len(fruits))             # จำนวนข้อมูล

# ตรวจสอบ
if "แอปเปิล" in fruits:
    print("มีแอปเปิล")
```

---

## ระยะที่ 3: ฟังก์ชัน (Functions) - สัปดาห์ที่ 9-12

### ฟังก์ชันคืออะไร?
```python
# ฟังก์ชัน = ชุดคำสั่งที่ทำงานเฉพาะ
# เหมือนสูตรอาหาร ใส่วัตถุดิบ ได้อาหาร

def greet():
    print("สวัสดี!")

# เรียกใช้ฟังก์ชัน
greet()  # สวัสดี!
greet()  # สวัสดี!
```

### ฟังก์ชันที่รับข้อมูล
```python
def greet(name):
    print(f"สวัสดี {name}!")

greet("จอห์น")    # สวัสดี จอห์น!
greet("แมรี่")    # สวัสดี แมรี่!
```

### ฟังก์ชันที่คืนค่า
```python
def add(a, b):
    return a + b

result = add(5, 3)    # 8
print(result)         # 8

def calculate_area(width, height):
    area = width * height
    return area

room_area = calculate_area(10, 12)
print(f"พื้นที่ห้อง: {room_area} ตารางเมตร")
```

---

## ระยะที่ 4: โปรเจคปฏิบัติ (สัปดาห์ที่ 13-16)

### โปรเจค 1: เครื่องคิดเลข
```python
def calculator():
    print("=== เครื่องคิดเลข ===")
    
    num1 = float(input("ตัวเลขที่ 1: "))
    operator = input("เลือกการคำนวณ (+, -, *, /): ")
    num2 = float(input("ตัวเลขที่ 2: "))
    
    if operator == "+":
        result = num1 + num2
    elif operator == "-":
        result = num1 - num2
    elif operator == "*":
        result = num1 * num2
    elif operator == "/":
        if num2 != 0:
            result = num1 / num2
        else:
            print("ไม่สามารถหารด้วย 0 ได้")
            return
    else:
        print("เลือกการคำนวณไม่ถูกต้อง")
        return
    
    print(f"ผลลัพธ์: {result}")

calculator()
```

### โปรเจค 2: เกมทายตัวเลข
```python
import random

def guessing_game():
    print("=== เกมทายตัวเลข ===")
    print("ฉันคิดตัวเลข 1-100")
    
    secret_number = random.randint(1, 100)
    attempts = 0
    
    while True:
        guess = int(input("ทายเลข: "))
        attempts += 1
        
        if guess == secret_number:
            print(f"ถูกต้อง! คุณทายได้ใน {attempts} ครั้ง")
            break
        elif guess < secret_number:
            print("เลขที่คิดใหญ่กว่านี้")
        else:
            print("เลขที่คิดเล็กกว่านี้")

guessing_game()
```

### โปรเจค 3: ระบบจัดการนักเรียน
```python
students = []

def add_student():
    name = input("ชื่อนักเรียน: ")
    age = int(input("อายุ: "))
    grade = input("เกรด: ")
    
    student = {
        "name": name,
        "age": age,
        "grade": grade
    }
    students.append(student)
    print(f"เพิ่ม {name} เรียบร้อย")

def show_students():
    if not students:
        print("ไม่มีนักเรียน")
        return
    
    print("=== รายชื่อนักเรียน ===")
    for i, student in enumerate(students, 1):
        print(f"{i}. {student['name']} อายุ {student['age']} เกรด {student['grade']}")

def main():
    while True:
        print("\n=== ระบบจัดการนักเรียน ===")
        print("1. เพิ่มนักเรียน")
        print("2. ดูรายชื่อ")
        print("3. ออก")
        
        choice = input("เลือก: ")
        
        if choice == "1":
            add_student()
        elif choice == "2":
            show_students()
        elif choice == "3":
            print("ขอบคุณ!")
            break
        else:
            print("เลือกไม่ถูกต้อง")

main()
```

---

## ระยะที่ 5: ขยายความรู้ (สัปดาห์ที่ 17-24)

### การจัดการไฟล์
```python
# เขียนไฟล์
with open("data.txt", "w", encoding="utf-8") as file:
    file.write("สวัสดี\n")
    file.write("Hello World\n")

# อ่านไฟล์
with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()
    print(content)

# อ่านทีละบรรทัด
with open("data.txt", "r", encoding="utf-8") as file:
    for line in file:
        print(line.strip())
```

### การจัดการข้อผิดพลาด
```python
def safe_divide(a, b):
    try:
        result = a / b
        return result
    except ZeroDivisionError:
        print("ไม่สามารถหารด้วย 0 ได้")
        return None
    except ValueError:
        print("ข้อมูลไม่ถูกต้อง")
        return None

# ใช้งาน
result = safe_divide(10, 2)  # 5.0
result = safe_divide(10, 0)  # ไม่สามารถหารด้วย 0 ได้
```

### Object-Oriented Programming (OOP)
```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.grades = []
    
    def add_grade(self, grade):
        self.grades.append(grade)
    
    def get_average(self):
        if not self.grades:
            return 0
        return sum(self.grades) / len(self.grades)
    
    def info(self):
        avg = self.get_average()
        print(f"ชื่อ: {self.name}")
        print(f"อายุ: {self.age}")
        print(f"คะแนนเฉลี่ย: {avg:.2f}")

# ใช้งาน
student1 = Student("จอห์น", 20)
student1.add_grade(85)
student1.add_grade(92)
student1.add_grade(78)
student1.info()
```

---

## ระยะที่ 6: Web Development (สัปดาห์ที่ 25-32)

### HTML พื้นฐาน
```html
<!DOCTYPE html>
<html>
<head>
    <title>เว็บไซต์แรก</title>
</head>
<body>
    <h1>สวัสดี!</h1>
    <p>นี่คือเว็บไซต์แรกของฉัน</p>
    <button onclick="sayHello()">คลิกที่นี่</button>
    
    <script>
        function sayHello() {
            alert("สวัสดี!");
        }
    </script>
</body>
</html>
```

### Flask (Python Web Framework)
```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def home():
    return '<h1>สวัสดี!</h1>'

@app.route('/calculator')
def calculator():
    return '''
    <form method="POST">
        <input type="number" name="num1" placeholder="ตัวเลขที่ 1">
        <input type="number" name="num2" placeholder="ตัวเลขที่ 2">
        <button type="submit">คำนวณ</button>
    </form>
    '''

@app.route('/calculator', methods=['POST'])
def calculate():
    num1 = float(request.form['num1'])
    num2 = float(request.form['num2'])
    result = num1 + num2
    return f'<h1>ผลลัพธ์: {result}</h1>'

if __name__ == '__main__':
    app.run(debug=True)
```

---

## ระยะที่ 7: Database (สัปดาห์ที่ 33-40)

### SQLite พื้นฐาน
```python
import sqlite3

# เชื่อมต่อฐานข้อมูล
conn = sqlite3.connect('students.db')
cursor = conn.cursor()

# สร้างตาราง
cursor.execute('''
    CREATE TABLE IF NOT EXISTS students (
        id INTEGER PRIMARY KEY,
        name TEXT NOT NULL,
        age INTEGER,
        grade TEXT
    )
''')

# เพิ่มข้อมูล
cursor.execute("INSERT INTO students (name, age, grade) VALUES (?, ?, ?)",
               ("จอห์น", 20, "A"))

# ดึงข้อมูล
cursor.execute("SELECT * FROM students")
rows = cursor.fetchall()
for row in rows:
    print(row)

# ปิดการเชื่อมต่อ
conn.commit()
conn.close()
```

---

## ระยะที่ 8: การเป็นมืออาชีพ (สัปดาห์ที่ 41-52)

### Git & GitHub
```bash
# ติดตั้ง Git
git --version

# สร้าง Repository
git init
git add .
git commit -m "Initial commit"

# เชื่อมต่อ GitHub
git remote add origin https://github.com/username/repo.git
git push -u origin main
```

### Testing
```python
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5
    assert add(-1, 1) == 0
    assert add(0, 0) == 0

# รัน pytest
# pytest test_file.py
```

### Documentation
```python
def calculate_area(width, height):
    """
    คำนวณพื้นที่สี่เหลี่ยมผืนผ้า
    
    Args:
        width (float): ความกว้าง
        height (float): ความยาว
    
    Returns:
        float: พื้นที่
    
    Example:
        >>> calculate_area(10, 5)
        50.0
    """
    return width * height
```

---

## ทักษะสำคัญที่ต้องมี

### 1. Problem Solving
- แยกปัญหาใหญ่เป็นปัญหาเล็ก
- คิดเป็นขั้นตอน
- ทดสอบและแก้ไข

### 2. Debugging
- หาจุดผิดพลาด
- ใช้ print() ตรวจสอบ
- อ่าน Error Message

### 3. Research Skills
- ค้นหาใน Google
- อ่าน Documentation
- ใช้ Stack Overflow

### 4. Version Control
- Git พื้นฐาน
- GitHub
- การทำงานร่วมกัน

---

## การพัฒนาต่อ

### Web Development
- **Frontend**: HTML, CSS, JavaScript, React
- **Backend**: Python (Django/Flask), Node.js
- **Database**: PostgreSQL, MongoDB

### Mobile Development
- **iOS**: Swift
- **Android**: Java/Kotlin
- **Cross-platform**: React Native, Flutter

### Data Science
- **Libraries**: NumPy, Pandas, Matplotlib
- **Machine Learning**: scikit-learn, TensorFlow
- **Statistics**: R, Python

### Game Development
- **Engines**: Unity (C#), Unreal (C++)
- **Languages**: C++, C#, Python

---

## Timeline การเรียนรู้

### เดือนที่ 1-2: พื้นฐาน
- ความเข้าใจโปรแกรม
- Python basics
- Variables, Operations

### เดือนที่ 3-4: Control Flow
- If-else statements
- Loops (for, while)
- Functions

### เดือนที่ 5-6: Data Structures
- Lists, Dictionaries
- File handling
- Error handling

### เดือนที่ 7-8: OOP & Projects
- Classes and Objects
- ทำโปรเจคเล็ก
- การแก้ปัญหา

### เดือนที่ 9-12: Advanced Topics
- Web development
- Database
- Git & GitHub
- Testing

---

## ตัวอย่างแนวคิด Career Path

### Junior Developer (0-2 ปี)
- เขียนโค้ดพื้นฐาน
- ทำงานใต้การดูแล
- เรียนรู้ระบบงาน

### Mid-level Developer (2-5 ปี)
- พัฒนา feature ใหม่
- แก้ปัญหาซับซ้อน
- ออกแบบระบบ

### Senior Developer (5+ ปี)
- นำทีม
- ตัดสินใจทางเทคนิค
- สอนคนใหม่

### ตำแหน่งที่เป็นไปได้
- Web Developer
- Software Engineer
- Data Scientist
- DevOps Engineer
- Technical Lead

---

**สำคัญ:** การเรียนรู้เขียนโปรแกรมต้องใช้เวลาและการฝึกฝนอย่างสม่ำเสมอ เริ่มต้นด้วยการทำโปรเจคเล็กๆ และค่อยๆ ขยายความรู้ไปเรื่อยๆ