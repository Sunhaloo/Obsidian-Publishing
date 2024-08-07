---
Alias: Computer Programming ( Semester 1 Labsheet 4 ) - Week 4
Tag: uni, python, uom, lab
Module: ICDT 1201Y
Author: S.Sunhaloo
Date: 2024-08-05
Status: Completed
---

### My Links

- [[Computer Programming - Labsheet 4#Socials | Link to Socials]]

---

# Question 1

```python

# exception handling
try:
	# ask the user to enter number
	user_num = float(input("\nPlease Enter A Number: "))

	# check if number is either even or odd
	if ( user_num % 2 ) == 0:
		# this means that the number the user entered is Even
		print("\nEven\n")
	else:
		# if it's not even; its going to be odd
		print("\nOdd\n")
except ValueError:
	print("\nPlease Enter Numbers Only!!!\n")

```

# Question 2

```python

# exception handling
try:
	# ask the user to enter 2 numbers
	num1 = float(input("\nPlease Enter Number 1: "))
	num2 = float(input("Please Enter Number 2: "))

	# calculate the sum of numbers
	sum = num1  + num2

	# check if sum is between 15 and 20
	if sum > 15 and sum < 20:
		print(f"\nSum was {sum:0.2f}; Hence Return {20}\n")
	else:
		print(f"\nThe Sum was: {sum:0.2f} ( 2 dp )\n")
except ValueError:
	print("\nPlease Enter Numbers Only!!!\n")

```

# Question 3

```python

# create a variable that will hold the number '0'
number = 0

# iterate until number becomes 100
# continue to iterate while variable `number` is less or equal to 100
while number <= 100:
	# output the numbers
	print(f"{number}", end=" | ")
	# increment the `number` variable by 5
	number += 5

```

# Question 4

```python

# exception handling
try:
	# ask the user to enter an integer value
	n = int(input("\nPlease Enter A Number: "))

	# check if `n` is greater than 100 or not
	if n > 100:
		print("\nWrong Input\n")
	else:
		print("\nThe Factors of Number '{n}':\n")
		# iterate from 1 to `n + 1`
		# factors starts with '1'
		for x in range(1, n + 1):
			# check if value is a factor
			if ( n % x ) == 0:
				# it is a factor if not remainder
				# output the value
				print(x)
except ValueError:
	print("\nPlease Enter Integer Numbers Only!!!\n")

```

# Question 5

```python

# import math libary / module
import math

# exception handling
try:
	# ask the user to enter a radius
	radius = float(input("\nPlease Enter Radius of Sphere ( in cm ): "))

	# check if radius entered is not a non-zero or negative value
	if radius == 0:
		print("\nRadius of Sphere Cannot be 0!!!\n")
	elif radius < 0:
		print("\nRadius / Length Cannot be Negative!!!\n")

	# if radius is a non-zero value ---> calculate the surface area
	surface_area = 4 * math.pi * math.pow(radius, 2)

	# output the results of `surface_area` to user
	print(f"\nThe Surface Area of Sphere with Radius {radius:0.2f} ( 2 dp ) = {surface_area:0.2f} cm^2 ( 2 dp )\n")

except ValueError:
	print("\nPlease Enter Numbers Only!!!\n")

```

# Question 6

```python

# variable 'temp_in_c' will hold the temperature in Celcius
temp_in_c = 60
# variable 'temp_in_f' will hold the temperature in Fahrenheit
temp_in_f = 45

# Celcius ---> Fahrenheit
calculated_f_temp = (temp_in_c * ( 9 / 5 )) + 32

# Fahrenheit ---> Celcius
calculated_c_temp = ( temp_in_f - 32 ) * (5 / 9 )

# output the results
print(f"\n{temp_in_c} Degree Celcius = {calculated_f_temp:0.0f} Fahrenheit")
print(f"{temp_in_f} Fahrenheit = {calculated_c_temp:0.0f} Celcius\n")

```

# Question 7

```python

# Formula: dog_age = ( 10.5 * 2 ) + ( 4 * ( human_years - 2 ))

# exception handling
try:
	# ask the user to enter dog's age
	human_years = int(input("\nPlease Enter Age of Dog ( in Human Years ): "))

	# calculate the actual "dog" years
	dog_age = ( 10.5 * 2 ) + ( 4 * ( human_years - 2 ))

	# output the results
	print(f"\nThe Age in Dog Years is: {dog_age:0.0f}\n")
except ValueError:
	print("\nPlease Enter Integer Number Only!!!\n")

```

# Question 8

```python

# import time module
import time

# exception handling
try:
	# ask the user to enter his name
	name = input("\nPlease Enter Your Name: ")
	# ask the user to enter his salary
	salary = float(input("Please Enter Your Salary: "))
	# ask the user to enter the number of dependents
	num_dependents = int(input("Please Enter Number of Dependents: "))

	# check if number of dependents in greater than 1
	if num_dependents <= 0:
		# output appropriate message
		print("\nNumber to Dependents Must be Greater or Equal to 1!!!\n")
		# exit the program
		word = "Exiting Program..."

		# output `word` in slow motion
		for i in word:
			print(i, end="", flush=True)
			time.sleep(0.2)
		
		time.sleep(0.2)

		# actually exit the program
		exit()

	# check how much to deduct from salary based on number of dependents
	# number of dependents = 1
	if num_dependents == 1:
		remaining_salary = salary - 110000
	# number of dependents = 2
	elif num_dependents == 2:
		remaining_salary = salary - 190000
	# number of dependents = 3
	elif num_dependents == 3:
		remaining_salary = salary - 275000
	# number of dependents >= 4
	elif num_dependents >= 4:
		remaining_salary = salary - 355000
		
	# calculate the tax on the remaining salary
	if remaining_salary <= 0 and remaining_salary <= 50000:
		# only need to calculate tax on remaining amount
		tax_amount = remaining_salary * 0.15
	elif remaining_salary > 50000 and remaining_salary <= 120000:
		# need to calculate for the first 50k
		tax_amount = ( 50000 * 0.15 ) + (( remaining_salary - 50000 ) * 0.20)
	elif remaining_salary >= 120000:
		# need to calculate for first 50k + next 70k
		tax_amount = ( 50000 * 0.15 ) + ( 70000 * 0.20 ) + (( remaining_salary - 70000 ) * 0.25)
	
	print(f"\nTax Payable By {name} = Rs {tax_amount:0.2f}\n")

	# tell the user that they do / do not need to pay tax
	if tax_amount <= 0:
		print("As Tax Payable is Less than or Equal to 0 ==> No need to pay Tax\n")
	else:
		print('-'*50)
		print(f"\nYou need to pay Rs {abs(tax_amount):0.2f}\n")
except ValueError:
	print("\nPlease Enter Integer Numbers Only!!!\n")

```

# Question 9

```python

# import the datetime library with only the part 'datetime'
from datetime import datetime
# import time library / module
import time

# get current year
current_year = datetime.now().year
'''
	I think it uses the OS's date as backend )
	Then again, I don't really know!
	Need to learn about it
'''

# output the current year
print()
print('-'*50)
print(f"The Current Year is {current_year}")
print('-'*50)

# exception handling
try:
	# ask the user to enter his name
	name = input("\nPlease Enter Your Name: ")
	# ask the user to enter his year of birth
	birth_year = int(input("Please Enter Year of Birth: "))

	# check if birth year is in range ( does not exceeds current year )
	if birth_year > current_year:
		print("\nInvalid Birth Year\n")
		# exit the program
		word = "Exiting Program..."

		# output `word` in slow motion
		for i in word:
			print(i, end="", flush=True)
			time.sleep(0.2)
		
		time.sleep(0.2)

		# actually exit the program
		exit()

	# calculate the age of user
	user_age = current_year - birth_year

	# output the result based on '18' year old condition
	if user_age < 18:
		print(f"\n{name} is still a child at {user_age} year(s) old\n")
	else:
		print(f"\n{name} is an adult at {user_age} years old")
except ValueError:
	print("\nPlease Enter Integer Number Only!!!\n")

```

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!