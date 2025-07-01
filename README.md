1)b )
from datetime import date

name = input("Enter the name of the person: ") 
birth_year = int(input("Enter year of birth: "))

current_year = date.today().year
age = current_year - birth_year

if age >= 60:
    print(f"{name} is {age} years old and is a Senior Citizen.")
else:
    print(f"{name} is {age} years old and is NOT a Senior Citizen.")

______________________________________________________________________________________________________________________________________________________________________-

1)a) 

name = input("Enter the name of the student: ")
usn = input("Enter the USN of the student: ")
m1 = int(input("Enter marks in Subject 1: "))
m2 = int(input("Enter marks in Subject 2: "))
m3 = int(input("Enter marks in Subject 3: "))

total = m1 + m2 + m3
percentage = total / 3

print("\n--- Student Details ---")
print(f"Name       : {name}")
print(f"USN        : {usn}")
print(f"Marks      : {m1}, {m2}, {m3}")
print(f"Total      : {total}")
print(f"Percentage : {percentage:.2f}%")

____________________________________________________________________________________________________________________________________________________________________-
2a)   5 

n = int(input("Enter how many Fibonacci numbers to print: "))
a, b = 0, 1

print(f"\nFibonacci sequence with {n} terms:")
for i in range(n):
    print(a, end=" ")
    a, b = b, a + b

__________________________________________________________________________________________________________________________________________________________________
2b)   7 and 4 

def factorial(n):
    return 1 if n == 0 or n == 1 else n * factorial(n - 1)

n = int(input("Enter value of n: "))
r = int(input("Enter value of r (0 ≤ r ≤ n): "))

if r < 0 or r > n:
    print("Invalid input! r should be between 0 and n.")
else:
    nCr = factorial(n) // (factorial(r) * factorial(n - r))
    print(f"{n}C{r} = {nCr}")
___________________________________________________________________________________________________________________________________________________________________
3)   5 

from math import sqrt

n = int(input("Enter how many numbers: "))
numbers = []

for i in range(n):
    num = float(input(f"Enter number {i+1}: "))
    numbers.append(num)

mean = sum(numbers) / n
variance = sum((x - mean) ** 2 for x in numbers) / n
std_dev = sqrt(variance)

print(f"\nNumbers: {numbers}")
print(f"Mean              : {mean:.2f}")
print(f"Variance          : {variance:.2f}")
print(f"Standard Deviation: {std_dev:.2f}")
______________________________________________________________________________________________________________________________________________________________________
4) 52231449

num_str = input("Enter a multi-digit number: ")
print(f"The number entered is: {num_str}")
print("Digit Frequencies:")

for digit in sorted(set(num_str)):
    print(f"Digit {digit} occurs {num_str.count(digit)} time(s)")

_____________________________________________________________________________________________________________________________________________________________________
5 )  name.txt 

import os
import string

filename = input("Enter the filename: ")

if not os.path.isfile(filename):
    print(f"File '{filename}' does not exist.")
    exit()

with open(filename, "r") as file:
    text = file.read()

for ch in string.punctuation:
    text = text.replace(ch, " ")

words = text.lower().split()

word_freq = {}
for word in words:
    if word in word_freq:
        word_freq[word] += 1
    else:
        word_freq[word] = 1

sorted_words = sorted(word_freq.items(), key=lambda x: x[1], reverse=True)

print("\nTop 10 Most Frequent Words:")
print("-" * 35)
for word, count in sorted_words[:10]:
    print(f"{word} : {count} time(s)")



import sys
def DivExp(a,b):
    assert a>0,"a should be greater than 0"
    try:c=a/b
    except ZeroDivisionError:
        print("value of b cannot be zero")
        sys.exit(0)
    else:
        return c
val1=int(input("enter a value for a:"))
val2=int(input("enter a value for b:"))
val3=DivExp(val1,val2)
print(val1,"/",val2,"=",val3)

____________________________________________________________________________________________________________________________________________________________________
6 

import os 
import sys 

fname = input("Enter the filename whose contents are to be sorted: ")  # sample file Text.txt 

if not os.path.isfile(fname): 
    print("File", fname, "doesn't exist") 
    sys.exit(0) 

with open(fname, "r") as infile: 
    myList = infile.readlines() 

lineList = [line.strip() for line in myList] 
lineList.sort()  # Sort the list 

with open("sorted.txt", "w") as outfile: 
    for line in lineList: 
        outfile.write(line + "\n") 

if os.path.isfile("sorted.txt"): 
    print("\nFile containing sorted content 'sorted.txt' created successfully.") 
    print("sorted.txt contains", len(lineList), "lines.") 
    print("Contents of sorted.txt:") 
    print("==========================================================") 
     
    with open("sorted.txt", "r") as rdFile: 
        for line in rdFile: 
            print(line, end="") 
______________________________________________________________________________________________________________________________________________________________________
7)  

import os 
import sys 
import pathlib 
import zipfile 
dirName = input("Enter Directory name that you want to backup: ") 
if not os.path.isdir(dirName): 
    print("Directory", dirName, "doesn’t exist") 
    sys.exit(0) 
curDirectory = pathlib.Path(dirName) 
with zipfile.ZipFile("myZip.zip", mode="w") as archive: 
    for file_path in curDirectory.rglob("*"): 
        archive.write(file_path, arcname=file_path.relative_to(curDirectory)) 
if os.path.isfile("myZip.zip"): 
    print("Archive", "myZip.zip", "created successfully") 
else: 
    print("Error in creating zip archive") 
__________________________________________________________________________________________________________________________________________________________________
8

import sys 
def DivExp(a, b): 
    assert a > 0, "a should be greater than 0" 
    try: 
        c = a / b 
    except ZeroDivisionError: 
        print("Value of b cannot be zero") 
        sys.exit(0) 
    else: 
        return c 
val1 = int(input("Enter a value for a: ")) 
val2 = int(input("Enter a value for b: ")) 
val3 = DivExp(val1, val2) 
print(val1, "/", val2, "=", val3) 

__________________________________________________________________________________________________________________________________________________________________________
9)

class Complex:
    def __init__(self, real, imag):
        self.real = real
        self.imag = imag

    def __add__(self, other):
        real_sum = self.real + other.real
        imag_sum = self.imag + other.imag
        return Complex(real_sum, imag_sum)

    def __str__(self):
        return f"{self.real} + {self.imag}i"


a = int(input("Enter real part of first complex number: "))
b = int(input("Enter imaginary part of first complex number: "))
c = int(input("Enter real part of second complex number: "))
d = int(input("Enter imaginary part of second complex number: "))

# Creat
c1 = Complex(a, b)
c2 = Complex(c, d)

# Sum
c3 = c1 + c2


print(f"The sum of {c1} and {c2} is: {c3}")

______________________________________________________________________________________________________________________________________________________________________
10)

class Student:
    def __init__(self, name="", usn="", score=None):
        if score is None:
            score = [0, 0, 0, 0]
        self.name = name
        self.usn = usn
        self.score = score

    def getMarks(self):
        self.name = input("Enter student Name: ")
        self.usn = input("Enter student USN: ")
        self.score[0] = int(input("Enter marks in Subject 1: "))
        self.score[1] = int(input("Enter marks in Subject 2: "))
        self.score[2] = int(input("Enter marks in Subject 3: "))
        self.score[3] = self.score[0] + self.score[1] + self.score[2]

    def display(self):
        percentage = self.score[3] / 3
        spcstr = "=" * 81
        print(spcstr)
        print("SCORE CARD DETAILS".center(81))
        print(spcstr)
        print("%15s %12s %8s %8s %8s %8s %12s" % ( "NAME", "USN", "MARKS1", "MARKS2", "MARKS3", "TOTAL", "PERCENTAGE"))
           
        print(spcstr)
        print("%15s %12s %8d %8d %8d %8d %12.2f" % (  self.name, self.usn, self.score[0], self.score[1], self.score[2], self.score[3], percentage))
          
           
        print(spcstr)

def main():
    s1 = Student()
    s1.getMarks()
    s1.display()

if __name__ == "__main__":
    main()

_____________________________________________________________________________________________________________________________________________________________________


class Student:
    def __init__(self, name, s1, s2, s3):
        self.name = name
        self.s1 = s1
        self.s2 = s2
        self.s3 = s3
        self.total = s1 + s2 + s3
        self.percentage = (self.total / 300) * 100

    def __str__(self):
        return (
            f"Score Card:\n"
            f"Name: {self.name}\n"
            f"Subject 1: {self.s1}\n"
            f"Subject 2: {self.s2}\n"
            f"Subject 3: {self.s3}\n"
            f"Total: {self.total} / 300\n"
            f"Percentage: {self.percentage:.2f}%")
        

name = input("Enter the student name: ")
s1 = float(input("Enter the marks for subject 1: "))
s2 = float(input("Enter the marks for subject 2: "))
s3 = float(input("Enter the marks for subject 3: "))

student = Student(name, s1, s2, s3)

print(student)

_______________________________________________________________________________________________________________________________________________________________________
>>>>>>birthday<<<<<<<

from datetime import datetime

b = input("Enter birthday (YYYY-MM-DD): ")
bd = datetime.strptime(b, "%Y-%m-%d")
now = datetime.now()

age = now.year - bd.year - ((now.month, now.day) < (bd.month, bd.day))
print(f"\nYou are {age} years old.")

next_bd = datetime(now.year, bd.month, bd.day)
if next_bd <= now:
    next_bd = next_bd.replace(year=now.year + 1)

delta = next_bd - now
d, h = delta.days, delta.seconds // 3600
m, s = (delta.seconds % 3600) // 60, delta.seconds % 60

print(f"\nTime until next birthday: {d}d {h}h {m}m {s}s")
_________________________________________________________________________________________________________________________________________________________________________

>>>>>>>to read and write on files<<<<<<<<<<<

fname = "sample.txt"


with open(fname, "w") as f:
    f.write("Hello!\nThis is a file example.\nEnjoy coding!")


with open(fname) as f:
    content = f.read()

print("File contents:\n", content)
__________________________________________________________________________________________________________________________________________________________________________
>>>>>>>>>>to read certain amount of characters from file<<<<<<<<<<<



with open("demo.txt", "w") as f:
    f.write("Python makes file handling easy.")


with open("demo.txt") as f:
    data = f.read(10)

print("First 10 characters:", data)

______________________________________________________________________________________________________________________________________________________________________

>>>>that searches a directory and all of its subdirectories,<<<<,

import os

path = input("Enter directory path: ")
suffix = input("Enter file suffix (e.g., .txt): ")

matches = []

for root, dirs, files in os.walk(path):
    for file in files:
        if file.endswith(suffix):
            matches.append(os.path.join(root, file))

print("\nFiles found:")
for m in matches:
    print(m)

____________________________________________________________________________________________________________________________________________________________________


>>>>>named point_in_circle that takes a Circle<<<<<<

import math

class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

class Circle:
    def __init__(self, x, y, r):
        self.center = Point(x, y)
        self.radius = r

def point_in_circle(circle, point):
    dx = point.x - circle.center.x
    dy = point.y - circle.center.y
    distance = math.hypot(dx, dy)
    return distance <= circle.radius

# Example usage
c = Circle(0, 0, 5)
p = Point(3, 4)

print(point_in_circle(c, p))  # True, since distance = 5

_______________________________________________________________________________________________________________________________________________________________

>>>>rect_in_circle that takes a Circle and a Rectangle and returns True<<<<,

import math

class Point:
    def __init__(self, x, y): self.x, self.y = x, y

class Circle:
    def __init__(self, x, y, r): self.center, self.radius = Point(x, y), r

class Rectangle:
    def __init__(self, x, y, w, h): self.x, self.y, self.w, self.h = x, y, w, h

def point_in_circle(circ, pt):
    return math.hypot(pt.x - circ.center.x, pt.y - circ.center.y) <= circ.radius

def rect_in_circle(circ, rect):
    corners = [
        Point(rect.x, rect.y),
        Point(rect.x + rect.w, rect.y),
        Point(rect.x, rect.y + rect.h),
        Point(rect.x + rect.w, rect.y + rect.h)
    ]
    return all(point_in_circle(circ, p) for p in corners)


c = Circle(0,0,10)
r = Rectangle(-3,-3,6,6)
print(rect_in_circle(c,r)) 

______________________________________________________________________________________________________________________________________________________________


>>>>>>to find if a point lies on or inside a rectangle<<<<<<<<<,

class Point:
    def __init__(self, x, y): self.x, self.y = x, y

class Rectangle:
    def __init__(self, x, y, w, h):  # (x,y)=bottom-left
        self.x, self.y, self.w, self.h = x, y, w, h

    def contains(self, p):
        return (self.x <= p.x <= self.x + self.w) and (self.y <= p.y <= self.y + self.h)

# Example
r = Rectangle(0, 0, 5, 5)
p = Point(3, 4)
print(r.contains(p))  

p2 = Point(6, 4)
print(r.contains(p2)) 

____________________________________________________________________________________________________________________________________________________________________

>>>>>provide feedback on whether the guess is too low,<<<<<<,,,

num = random.randint(1, 10)
attempts = 0

while True:
    guess = int(input("Guess a number (1-10): "))
    attempts += 1
    if guess < num:
        print("Too low.")
    elif guess > num:
        print("Too high.")
    else:
        print(f"Correct! Attempts: {attempts}")
        break

______________________________________________________________________________________________________________________________________________________________


>>>>>count the number of times<<<<<<<<<<

word = input("Enter a word: ").lower()
counts = {}

for ch in word:
    counts[ch] = counts.get(ch, 0) + 1

for k, v in counts.items():
    print(f"{k}: {v}")
__________________________________________________________________________________________________________________________________________________________________




