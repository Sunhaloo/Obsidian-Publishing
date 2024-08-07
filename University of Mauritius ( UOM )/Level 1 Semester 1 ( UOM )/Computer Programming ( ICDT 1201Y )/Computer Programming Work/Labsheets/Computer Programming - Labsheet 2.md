---
Alias: Computer Programming ( Semester 1 Labsheet 2 ) - Week 2
Tag: uni, python, uom, lab
Module: ICDT 1201Y
Author: S.Sunhaloo
Date: 2024-07-31
Status: Completed
---

### My Links

- [[Computer Programming - Labsheet 2#Socials | Link to Socials]]

---

# Scenario 1

```python

# ask the user to enter length
length = float(input("\nPlease Enter Length ( in m ): "))
# ask the user to enter width
width = float(input("Please Enter Width ( in m ): "))

# calculate the area
area = length * width

# output the value of `area` to user
print(f"\nThe Area is {area:0.2f}")

```

# Scenario 2

```python

# exception handling
try:
	# ask the user to enter number
	user_num = int(input("\nPlease Enter An Integer Value: "))

	# check if value entered is even or odd
	if user_num % 2 == 0:
		# if user's value is even
		print(f"\nYou Number {user_num} is Even!\n")
	else:
		# if user's value is odd
		print(f"\nYou Number {user_num} is Odd!\n")
except ValueError:
	print("\nPlease Enter Integer Values Only!!!\n")

```

# Scenario 3

```python

import time

# for asthetic purposes
word = "\nCalculating...\n"

# output in slowmotion
for i in word:
	print(i, end="", flush=True)
	time.sleep(0.2)

# declare a variable and initialise it to 1
nat_num = 1
# create a total variable to hold the sum of natural numbers
total = 0

# calculate the sum of natural numbers
for i in range(100):
	total += nat_num
	nat_num += 1

# output the sum of 100 natural numbers
print(f"\nSum of First 100 Natural Numbers = {total}\n")

```

# Scenario 4

```python

# declare and intialise a variable that will become our least value
least_time = 999999999
# declare a variable that will keep track of date when least slept
specific_date = 0

# iterate through and ask the user to enter amount of time slept
for date in range(31):
	# ask the user to enter the time slept for each date
	current_time = int(
		input(f"\nPlease Enter Current Hours Slept on Day {date + 1}: ")
	)

	# check if current_time is less than least_time
	if current_time < least_time:
		# variable `least_time` takes that value
		least_time = current_time
		# find the date where we spent least time sleeping
		specific_date = date

# output the date for least time sleeping
print(f"\nDate Least Spent Sleeping: {specific_date + 1}\n")

```

# Scenario 5

```python

# ask the user to enter the mark
mark = int(input("\nPlease Enter Mark of Student: "))

# check mark entered is in range
if mark < 0 or mark > 100:
	print("\nMarks Entered are Out of Range!!!\n")
# if mark entered is in range
elif mark >= 90 and mark <= 100:
	print("\nGrade = 'A'\n")
elif mark >= 80 and mark <= 89:
	print("\nGrade = 'B'\n")
elif mark >= 70 and mark <= 79:
	print("\nGrade = 'C'\n")
elif mark >= 60 and mark <= 69:
	print("\nGrade = 'D'\n")
elif mark >= 0 and mark <= 60:
	print("\nGrade = 'F'\n")

```

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!