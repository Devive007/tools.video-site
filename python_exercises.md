# แบบฝึกหัด Python สำหรับผู้เริ่มต้น
## จากพื้นฐานสู่ระดับกลาง

### สัปดาห์ที่ 1: แบบฝึกหัดพื้นฐาน

#### Exercise 1: Variables และ Print
```python
# โจทย์: สร้างตัวแปรและแสดงผล
# 1. สร้างตัวแปร name ใส่ชื่อของคุณ
# 2. สร้างตัวแปร age ใส่อายุของคุณ  
# 3. แสดงผล "สวัสดี [ชื่อ] อายุ [อายุ] ปี"

# เฉลย:
name = "จอห์น"
age = 25
print(f"สวัสดี {name} อายุ {age} ปี")
```

#### Exercise 2: การคำนวณ
```python
# โจทย์: คำนวณพื้นที่สี่เหลี่ยมผืนผ้า
# รับค่าความกว้างและความยาว แล้วคำนวณพื้นที่

# เฉลย:
width = float(input("ความกว้าง: "))
height = float(input("ความยาว: "))
area = width * height
print(f"พื้นที่ = {area} ตารางเมตร")
```

#### Exercise 3: การแปลงหน่วย
```python
# โจทย์: แปลงอุณหภูมิจากเซลเซียสเป็นฟาเรนไฮต์
# สูตร: F = (C × 9/5) + 32

# เฉลย:
celsius = float(input("อุณหภูมิ (°C): "))
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius}°C = {fahrenheit}°F")
```

### สัปดาห์ที่ 2: If-Else

#### Exercise 4: ตรวจสอบเกรด
```python
# โจทย์: รับคะแนนและแสดงเกรด
# A: 80-100, B: 70-79, C: 60-69, D: 50-59, F: 0-49

# เฉลย:
score = int(input("คะแนน: "))

if score >= 80:
    grade = "A"
elif score >= 70:
    grade = "B"
elif score >= 60:
    grade = "C"
elif score >= 50:
    grade = "D"
else:
    grade = "F"

print(f"เกรดของคุณ: {grade}")
```

#### Exercise 5: ตรวจสอบปีอธิกสุรทิน
```python
# โจทย์: ตรวจสอบว่าปีนั้นเป็นปีอธิกสุรทินหรือไม่
# เงื่อนไข: หารด้วย 4 ลงตัว แต่หารด้วย 100 ไม่ลงตัว 
# หรือหารด้วย 400 ลงตัว

# เฉลย:
year = int(input("ปี: "))

if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):
    print(f"{year} เป็นปีอธิกสุรทิน")
else:
    print(f"{year} ไม่เป็นปีอธิกสุรทิน")
```

#### Exercise 6: เครื่องคิดเลขเบสิก
```python
# โจทย์: สร้างเครื่องคิดเลขที่รับตัวเลข 2 ตัว และเครื่องหมาย

# เฉลย:
num1 = float(input("ตัวเลขที่ 1: "))
operator = input("เครื่องหมาย (+, -, *, /): ")
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
        exit()
else:
    print("เครื่องหมายไม่ถูกต้อง")
    exit()

print(f"{num1} {operator} {num2} = {result}")
```

### สัปดาห์ที่ 3: Loops

#### Exercise 7: ตารางคูณ
```python
# โจทย์: แสดงตารางคูณจาก 1-12

# เฉลย:
number = int(input("ตารางคูณ: "))

for i in range(1, 13):
    result = number * i
    print(f"{number} × {i} = {result}")
```

#### Exercise 8: หาผลรวมของเลข 1-100
```python
# โจทย์: หาผลรวมของเลข 1 ถึง 100

# เฉลย:
total = 0
for i in range(1, 101):
    total += i

print(f"ผลรวม 1-100 = {total}")

# หรือใช้สูตร
n = 100
total = n * (n + 1) // 2
print(f"ผลรวม 1-100 = {total}")
```

#### Exercise 9: หาเลขคู่และเลขคี่
```python
# โจทย์: แสดงเลขคู่และเลขคี่จาก 1-20

# เฉลย:
even_numbers = []
odd_numbers = []

for i in range(1, 21):
    if i % 2 == 0:
        even_numbers.append(i)
    else:
        odd_numbers.append(i)

print("เลขคู่:", even_numbers)
print("เลขคี่:", odd_numbers)
```

#### Exercise 10: เกมทายตัวเลข
```python
# โจทย์: สร้างเกมทายตัวเลข 1-10

# เฉลย:
import random

secret_number = random.randint(1, 10)
max_attempts = 3

print("เกมทายตัวเลข 1-10 (3 ครั้ง)")

for attempt in range(1, max_attempts + 1):
    guess = int(input(f"ครั้งที่ {attempt}: "))
    
    if guess == secret_number:
        print("ถูกต้อง! คุณชนะ!")
        break
    elif guess < secret_number:
        print("เลขที่คิดใหญ่กว่า")
    else:
        print("เลขที่คิดเล็กกว่า")
    
    if attempt == max_attempts:
        print(f"หมดโอกาส! เลขที่คิดคือ {secret_number}")
```

### สัปดาห์ที่ 4: Lists

#### Exercise 11: จัดการรายการสินค้า
```python
# โจทย์: สร้างโปรแกรมจัดการรายการสินค้า

# เฉลย:
products = []

while True:
    print("\n=== ระบบจัดการสินค้า ===")
    print("1. เพิ่มสินค้า")
    print("2. ดูรายการสินค้า")
    print("3. ลบสินค้า")
    print("4. ออก")
    
    choice = input("เลือก: ")
    
    if choice == "1":
        product = input("ชื่อสินค้า: ")
        products.append(product)
        print(f"เพิ่ม {product} แล้ว")
    
    elif choice == "2":
        if products:
            print("รายการสินค้า:")
            for i, product in enumerate(products, 1):
                print(f"{i}. {product}")
        else:
            print("ไม่มีสินค้า")
    
    elif choice == "3":
        if products:
            print("สินค้าที่มี:")
            for i, product in enumerate(products, 1):
                print(f"{i}. {product}")
            
            try:
                index = int(input("เลือกลำดับที่จะลบ: ")) - 1
                if 0 <= index < len(products):
                    removed = products.pop(index)
                    print(f"ลบ {removed} แล้ว")
                else:
                    print("ลำดับไม่ถูกต้อง")
            except ValueError:
                print("กรุณาใส่ตัวเลข")
        else:
            print("ไม่มีสินค้าให้ลบ")
    
    elif choice == "4":
        print("ขอบคุณ!")
        break
    
    else:
        print("เลือกไม่ถูกต้อง")
```

#### Exercise 12: หาค่าสูงสุดและต่ำสุด
```python
# โจทย์: หาค่าสูงสุดและต่ำสุดใน list

# เฉลย:
numbers = []

print("ใส่ตัวเลข (พิมพ์ 'done' เพื่อจบ):")
while True:
    user_input = input("ตัวเลข: ")
    if user_input.lower() == 'done':
        break
    try:
        number = float(user_input)
        numbers.append(number)
    except ValueError:
        print("กรุณาใส่ตัวเลข")

if numbers:
    print(f"ตัวเลขทั้งหมด: {numbers}")
    print(f"ค่าสูงสุด: {max(numbers)}")
    print(f"ค่าต่ำสุด: {min(numbers)}")
    print(f"ค่าเฉลี่ย: {sum(numbers) / len(numbers):.2f}")
else:
    print("ไม่มีตัวเลข")
```

### สัปดาห์ที่ 5: Functions

#### Exercise 13: ฟังก์ชันคำนวณ
```python
# โจทย์: สร้างฟังก์ชันคำนวณทางคณิตศาสตร์

# เฉลย:
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b != 0:
        return a / b
    else:
        return "ไม่สามารถหารด้วย 0 ได้"

def power(a, b):
    return a ** b

def factorial(n):
    if n <= 1:
        return 1
    else:
        return n * factorial(n - 1)

# ทดสอบ
print("10 + 5 =", add(10, 5))
print("10 - 5 =", subtract(10, 5))
print("10 × 5 =", multiply(10, 5))
print("10 ÷ 5 =", divide(10, 5))
print("10^2 =", power(10, 2))
print("5! =", factorial(5))
```

#### Exercise 14: ฟังก์ชันตรวจสอบ
```python
# โจทย์: สร้างฟังก์ชันตรวจสอบต่างๆ

# เฉลย:
def is_even(number):
    return number % 2 == 0

def is_prime(number):
    if number < 2:
        return False
    for i in range(2, int(number ** 0.5) + 1):
        if number % i == 0:
            return False
    return True

def is_palindrome(text):
    text = text.lower().replace(" ", "")
    return text == text[::-1]

def count_vowels(text):
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count

# ทดสอบ
print("8 เป็นเลขคู่:", is_even(8))
print("17 เป็นเลขคู่:", is_even(17))
print("7 เป็นจำนวนเฉพาะ:", is_prime(7))
print("8 เป็นจำนวนเฉพาะ:", is_prime(8))
print("'racecar' เป็น palindrome:", is_palindrome("racecar"))
print("'hello' เป็น palindrome:", is_palindrome("hello"))
print("สระใน 'programming':", count_vowels("programming"))
```

### สัปดาห์ที่ 6: โปรเจครวม

#### Exercise 15: ระบบจัดการนักเรียน
```python
# โจทย์: สร้างระบบจัดการนักเรียนแบบสมบูรณ์

# เฉลย:
students = []

def add_student():
    name = input("ชื่อนักเรียน: ")
    age = int(input("อายุ: "))
    grades = []
    
    print("ใส่คะแนน (พิมพ์ 'done' เพื่อจบ):")
    while True:
        grade_input = input("คะแนน: ")
        if grade_input.lower() == 'done':
            break
        try:
            grade = float(grade_input)
            grades.append(grade)
        except ValueError:
            print("กรุณาใส่ตัวเลข")
    
    student = {
        'name': name,
        'age': age,
        'grades': grades
    }
    students.append(student)
    print(f"เพิ่ม {name} เรียบร้อย")

def show_students():
    if not students:
        print("ไม่มีนักเรียน")
        return
    
    print("\n=== รายชื่อนักเรียน ===")
    for i, student in enumerate(students, 1):
        avg = sum(student['grades']) / len(student['grades']) if student['grades'] else 0
        print(f"{i}. {student['name']} (อายุ {student['age']}) - เฉลี่ย: {avg:.2f}")

def search_student():
    if not students:
        print("ไม่มีนักเรียน")
        return
    
    name = input("ชื่อที่ต้องการหา: ")
    found = False
    
    for student in students:
        if name.lower() in student['name'].lower():
            avg = sum(student['grades']) / len(student['grades']) if student['grades'] else 0
            print(f"พบ: {student['name']} (อายุ {student['age']}) - เฉลี่ย: {avg:.2f}")
            print(f"คะแนนทั้งหมด: {student['grades']}")
            found = True
    
    if not found:
        print("ไม่พบนักเรียน")

def calculate_class_average():
    if not students:
        print("ไม่มีนักเรียน")
        return
    
    total_avg = 0
    count = 0
    
    for student in students:
        if student['grades']:
            student_avg = sum(student['grades']) / len(student['grades'])
            total_avg += student_avg
            count += 1
    
    if count > 0:
        class_avg = total_avg / count
        print(f"คะแนนเฉลี่ยของห้อง: {class_avg:.2f}")
    else:
        print("ไม่มีข้อมูลคะแนน")

def main():
    while True:
        print("\n=== ระบบจัดการนักเรียน ===")
        print("1. เพิ่มนักเรียน")
        print("2. ดูรายชื่อนักเรียน")
        print("3. ค้นหานักเรียน")
        print("4. คะแนนเฉลี่ยของห้อง")
        print("5. ออก")
        
        choice = input("เลือก: ")
        
        if choice == "1":
            add_student()
        elif choice == "2":
            show_students()
        elif choice == "3":
            search_student()
        elif choice == "4":
            calculate_class_average()
        elif choice == "5":
            print("ขอบคุณ!")
            break
        else:
            print("เลือกไม่ถูกต้อง")

if __name__ == "__main__":
    main()
```

### สัปดาห์ที่ 7: การทำงานกับไฟล์

#### Exercise 16: บันทึกและอ่านไฟล์
```python
# โจทย์: สร้างโปรแกรมบันทึกไดอารี่

# เฉลย:
import datetime

def write_diary():
    date = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    entry = input("เขียนไดอารี่: ")
    
    with open("diary.txt", "a", encoding="utf-8") as file:
        file.write(f"{date}: {entry}\n")
    
    print("บันทึกเรียบร้อย")

def read_diary():
    try:
        with open("diary.txt", "r", encoding="utf-8") as file:
            content = file.read()
            if content:
                print("=== ไดอารี่ ===")
                print(content)
            else:
                print("ไม่มีไดอารี่")
    except FileNotFoundError:
        print("ไม่พบไฟล์ไดอารี่")

def main():
    while True:
        print("\n=== ไดอารี่ ===")
        print("1. เขียนไดอารี่")
        print("2. อ่านไดอารี่")
        print("3. ออก")
        
        choice = input("เลือก: ")
        
        if choice == "1":
            write_diary()
        elif choice == "2":
            read_diary()
        elif choice == "3":
            print("ขอบคุณ!")
            break
        else:
            print("เลือกไม่ถูกต้อง")

if __name__ == "__main__":
    main()
```

### สัปดาห์ที่ 8: โปรเจคขั้นสูง

#### Exercise 17: เครื่องคิดเลขเต็มรูปแบบ
```python
# โจทย์: สร้างเครื่องคิดเลขที่มีประวัติการคำนวณ

# เฉลย:
import datetime

class Calculator:
    def __init__(self):
        self.history = []
    
    def add(self, a, b):
        result = a + b
        self.save_history(f"{a} + {b} = {result}")
        return result
    
    def subtract(self, a, b):
        result = a - b
        self.save_history(f"{a} - {b} = {result}")
        return result
    
    def multiply(self, a, b):
        result = a * b
        self.save_history(f"{a} × {b} = {result}")
        return result
    
    def divide(self, a, b):
        if b == 0:
            error = "ไม่สามารถหารด้วย 0 ได้"
            self.save_history(f"{a} ÷ {b} = {error}")
            return error
        result = a / b
        self.save_history(f"{a} ÷ {b} = {result}")
        return result
    
    def power(self, a, b):
        result = a ** b
        self.save_history(f"{a}^{b} = {result}")
        return result
    
    def save_history(self, calculation):
        timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        self.history.append(f"{timestamp}: {calculation}")
    
    def show_history(self):
        if not self.history:
            print("ไม่มีประวัติการคำนวณ")
            return
        
        print("=== ประวัติการคำนวณ ===")
        for record in self.history:
            print(record)
    
    def clear_history(self):
        self.history.clear()
        print("ล้างประวัติแล้ว")

def main():
    calc = Calculator()
    
    while True:
        print("\n=== เครื่องคิดเลข ===")
        print("1. บวก")
        print("2. ลบ")
        print("3. คูณ")
        print("4. หาร")
        print("5. ยกกำลัง")
        print("6. ดูประวัติ")
        print("7. ล้างประวัติ")
        print("8. ออก")
        
        choice = input("เลือก: ")
        
        if choice in ["1", "2", "3", "4", "5"]:
            try:
                a = float(input("ตัวเลขที่ 1: "))
                b = float(input("ตัวเลขที่ 2: "))
                
                if choice == "1":
                    result = calc.add(a, b)
                elif choice == "2":
                    result = calc.subtract(a, b)
                elif choice == "3":
                    result = calc.multiply(a, b)
                elif choice == "4":
                    result = calc.divide(a, b)
                elif choice == "5":
                    result = calc.power(a, b)
                
                print(f"ผลลัพธ์: {result}")
            
            except ValueError:
                print("กรุณาใส่ตัวเลข")
        
        elif choice == "6":
            calc.show_history()
        elif choice == "7":
            calc.clear_history()
        elif choice == "8":
            print("ขอบคุณ!")
            break
        else:
            print("เลือกไม่ถูกต้อง")

if __name__ == "__main__":
    main()
```

---

## แบบฝึกหัดเพิ่มเติม

### Challenge Problems

#### Challenge 1: FizzBuzz
```python
# โจทย์: พิมพ์เลข 1-100 แต่
# - ถ้าหารด้วย 3 ลงตัว พิมพ์ "Fizz"
# - ถ้าหารด้วย 5 ลงตัว พิมพ์ "Buzz"  
# - ถ้าหารด้วย 3 และ 5 ลงตัว พิมพ์ "FizzBuzz"

# เฉลย:
for i in range(1, 101):
    if i % 3 == 0 and i % 5 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```

#### Challenge 2: Password Generator
```python
# โจทย์: สร้าง password generator

# เฉลย:
import random
import string

def generate_password(length=8, include_upper=True, include_lower=True, 
                     include_digits=True, include_symbols=True):
    characters = ""
    
    if include_lower:
        characters += string.ascii_lowercase
    if include_upper:
        characters += string.ascii_uppercase
    if include_digits:
        characters += string.digits
    if include_symbols:
        characters += "!@#$%^&*"
    
    if not characters:
        return "ต้องเลือกอย่างน้อย 1 ชนิด"
    
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

# ทดสอบ
print("Password:", generate_password(12))
print("Password (เฉพาะตัวอักษร):", generate_password(8, include_digits=False, include_symbols=False))
```

#### Challenge 3: Hangman Game
```python
# โจทย์: สร้างเกมแฮงแมน

# เฉลย:
import random

def hangman():
    words = ["python", "programming", "computer", "algorithm", "function"]
    word = random.choice(words)
    guessed_letters = set()
    wrong_guesses = 0
    max_wrong = 6
    
    print("=== เกมแฮงแมน ===")
    print(f"คำศัพท์มี {len(word)} ตัวอักษร")
    
    while wrong_guesses < max_wrong:
        # แสดงคำศัพท์
        display_word = ""
        for letter in word:
            if letter in guessed_letters:
                display_word += letter + " "
            else:
                display_word += "_ "
        
        print(f"\nคำศัพท์: {display_word}")
        print(f"ทายผิด: {wrong_guesses}/{max_wrong}")
        print(f"ตัวอักษรที่ทายแล้ว: {', '.join(sorted(guessed_letters))}")
        
        # ตรวจสอบชนะ
        if all(letter in guessed_letters for letter in word):
            print(f"\nยินดีด้วย! คำศัพท์คือ '{word}'")
            break
        
        # รับทาย
        guess = input("ทายตัวอักษร: ").lower()
        
        if len(guess) != 1 or not guess.isalpha():
            print("กรุณาใส่ตัวอักษรเดียว")
            continue
        
        if guess in guessed_letters:
            print("ทายแล้ว")
            continue
        
        guessed_letters.add(guess)
        
        if guess in word:
            print("ถูกต้อง!")
        else:
            print("ผิด!")
            wrong_guesses += 1
    
    else:
        print(f"\nเกมจบ! คำศัพท์คือ '{word}'")

# เรียกใช้
hangman()
```

---

## เคล็ดลับการฝึกฝน

### 1. ฝึกทุกวัน
- อย่างน้อย 30 นาทีต่อวัน
- ทำแบบฝึกหัดเล็กๆ
- อย่าฝึกหนักเกินไป

### 2. Debug Skills
- ใช้ print() ตรวจสอบค่า
- อ่าน error message ให้เข้าใจ
- แก้ไขทีละขั้นตอน

### 3. Practice Makes Perfect
- ทำแบบฝึกหัดซ้ำ
- ปรับปรุงโค้ดเก่า
- คิดวิธีใหม่ในการแก้ปัญหา

### 4. ใช้ Resources
- Google เมื่อติดปัญหา
- อ่าน Python documentation
- ดูตัวอย่างจาก Stack Overflow

---

**สำคัญ:** การเรียนรู้ programming ต้องใช้การฝึกฝน เริ่มจากแบบฝึกหัดง่าย ๆ แล้วค่อยๆ เพิ่มความซับซ้อน