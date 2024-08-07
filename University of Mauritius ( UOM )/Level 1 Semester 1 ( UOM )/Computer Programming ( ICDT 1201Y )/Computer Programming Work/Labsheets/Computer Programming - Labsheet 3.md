---
Alias: Computer Programming ( Semester 1 Labsheet 3 ) - Week 3
Tag: uni, python, uom, lab
Module: ICDT 1201Y
Author: S.Sunhaloo
Date: 2024-07-31
Status: Completed
---

### My Links

- [[Computer Programming - Labsheet 3#Socials | Link to Socials]]

---

# Question 1

```python

print()

# output the number of rows
for i in range(4):
	# output the number of columns
	for j in range(6):
		print("*", end="")

	print()

print()

```

# Question 2

```python

import math

# ask the user to enter radius of circle
radius = float(input("\nPlease Enter Radius of Circle ( in cm ): "))

# calculate the area of circle
area = math.pi * math.pow(radius, 2)

# output the result to user
print(f"The Area of Cicle is = {area:0.2f} ( 2 dp )")

```

# Question 3

```python

# exception handling
try:
	# ask the user to enter his name
	name = input("\nPlease Enter Your Name: ")

	# ask thse user to enter his score
	score_1 = int(input("Please Enter Score for ICDT1016Y: "))
	score_2 = int(input("Please Enter Score for ICDT1201Y: "))

	# calculate the average score
	avg_score = (score_1 + score_2) / 2

	print("_" * 10)

	# output the result to user
	print(f"\nName: {name}")
	print(f"Your Average Score is {avg_score}\n")

	print("_" * 10)

	print()

# if user does not enter integer values
except ValueError:
	print("\nPlease Enter Integer Values Only for Scores!!!\n")

```

# Question 4

```python

# input values of variables
print("\nEnter Value for Speeds In Kilometer per Hour ( km/p )\n")

s1 = float(input("Please Enter Speed 's1': "))
s2 = float(input("Please Enter Speed 's2': "))
s3 = float(input("Please Enter Speed 's3': "))

print("\nEnter Value for Distance in Kilometer ( km )\n")

d1 = float(input("Please Enter Distance 'd1': "))
d2 = float(input("Please Enter Distance 'd2': "))
d3 = float(input("Please Enter Distance 'd3': "))

# find the total distance travelled
total_distance = d1 + d2 + d3

# find the total time
total_time = (d1 / s1) + (d2 / s2) + (d3 / s3)

# find the avarage speed
ave_speed = total_distance / total_time

# output the results to user
print(f"\nThe Total Distance Travelled = {total_distance:0.2f} km ( 2 dp)")
print(f"The Total Time Travelled = {total_time:0.2f} hr ( 2 dp)")
print(f"The Average Speed = {ave_speed:0.2f} km/h ( 2 dp)\n")


```

# Question 5

```python

# ask the user to enter number of hours worked
num_hours = int(input("\nPlease Enter Number of Hours Worked: "))
# ask the user to enter pay rate
pay_rate = float(input("Please Enter Pay Rate: "))

# calculate the salary
salary = num_hours * pay_rate

# output the salary of the user
print(f"\nThe Salaray = {salary}\n")


```

# Question 6

```python

import math

# exception handling
try:
	# ask the user to enter radius
	radius = float(input("\nPlease Enter Radius of Cylinder ( in cm ): "))
	# ask the user to enter height
	height = float(input("Please Enter Height of Cylinder ( in cm ): "))

	# total surface area of cicle
	area = (2 * math.pi * radius * height) + (2 * math.pi * math.pow(radius, 2))

	# output the result
	print(f"\nThe Total Surface Area of Cylinder = {area:0.2f} cm^2 ( 2 dp )\n")

except ValueError:
	print("\nPlease Enter Numbers Only!!!\n")


```

# Question 7

```python

# ask user to input depth
depth = float(input("\nPlease Enter Depth ( in m ): "))

# temperature in Celcius
temp_celcius = 10 * depth + 20
# temperature in Fahrenheit
temp_fahrenheit = 1.8 * temp_celcius + 32

# output the results
print(f"\nTemparature ( Degrees Celcius ) = {temp_celcius:0.2f} | Temparature ( Fahrenheit ) = {temp_fahrenheit:0.2f}\n")

```

# Question 8

```python

# ask the user to enter these values
distance = float(input("\nPlease Enter Distance ( in miles ): "))
mpg = float(input("Pleaes Enter the Miles per Gallon ( mpg ): "))
avg_cost = float(input("Please Enter Cost of Gallon of Gas ( in dollars ): "))

# calculate the number of gallons required
num_gallons = distance / mpg
# calculate the price for that amount of gallons needed
cost = avg_cost * num_gallons

# output the result  to user
print(f"\nNumber of Gallons Needed = {int(num_gallons)} Gallons")
print(f"Cost of {int(num_gallons)} Gallons = {cost:0.2f} Dollars")

```

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!