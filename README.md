#Calendar Lab
#Ryan Sattler, Graham Pankratz, Jacob Bussmann
#10/11/18

#User Input (Graham)
month = int(input("What is the month? (M/YYYY)"))
print('')
year = int(input("What is the year? (M/YYYY)"))

#Invalid input (Graham)
if month >= 13:
    print("Error: month not given in correct format.")

#Number of days in month (Graham)
elif month in (1,3,5,7,8,10,12):
    days = 31

elif month in (2,4,6,9,11):
    days = 30

elif month == 2:
    if year%4 == 0:
        days = 29
    else:
        days = 28

#Beginning day calculations (Graham)
century_digits = year//100
year_digits = year%100
value = year_digits + (year_digits//4)

if century_digits == 18:
    value = value + 2
    
if century_digits == 20:
    value = value + 6

if month == 1 and year%4 != 0:
    value = value + 1
  
elif month == 2:
    if year%4 == 0:
        value = value + 3
    else:
        value = value + 4

elif month in (3,11):
    value = value + 4

elif month in (4,7):
    value = value

elif month == 5:
    value = value + 2

elif month == 6:
    value = value + 5

elif month == 8:
    value = value + 3

elif month == 10:
    value = value + 1

elif month in (9,12):
    value = value + 6

value = (value + 1)%7
if value == 0:
    day_of_the_week = 7
else:
    day_of_the_week = value


#Output (Graham/Ryan)

print("")
print(month, "/", year)
print("Su Mo Tu We Th Fr Sa")


place=1

while place<=days:
    if place==1:
        print(''*(day_of_the_week-1),place,'\t')
    elif 2<=place<=9:
        print(place,'\t'),
        if day_of_the_week==7:
            print()
            day_of_the_week=0
        print()
    elif place>9:
        print(place, "\t"),
        if day_of_the_week==7:
            print()
            day_of_the_week=0
        print()
            
    place=place+1
    day_of_the_week = day_of_the_week+1



























        

    


