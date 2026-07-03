so now im officially gonna say welcome to python programming

here you are gonna learn how fast and how great python is at solving problems that in C would take a lot of lines

so without anything further lets continue with your first python project:


# **ex0**

so now you are asked to create a function named:

```python
ft_hello_garden()
```

the way we do it is by typing **def** and then the name of the function

so in our case we do:

```python
def ft_hello_garden():
```

python works with `:` so every function ends with `:`

the same thing happens with `if`, `else` and `elif`
thats right, in python it is called `elif`

python works with indentation and not like C which uses brackets

so to use another function such as `print()` inside your function, the new line needs to have 4 spaces after the line where you wrote the function

like:

```python
def ft_hello_garden():
    print("Hello, Garden Community!")
```

for this exercise you will not need a main

---

# **ex1**
ok now we are at ex1

we are asked to create a function named:

```python
ft_garden_name()
```

so as we learned:

```python
def ft_garden_name():
```

but the thing that we are asked to use is `input()`

so how do we use input?

first we are gonna learn how we declare variables in python

we just choose their name and assign them a value:

```python
a = 0
b = True
c = 2.2
```

based on the value given, python automatically determines if what you have written is an integer, string, boolean, float, etc.

so now how do we use input?

if we want a string we can say:

```python
a = input("Tell the user what to do: ")
```

`input()` always gives us a string

if we wanted a number, we could write:

```python
a = int(input("Tell the user what to do: "))
```

first `input()` gets the value from the user and then `int()` changes it into an integer

but in this exercise the garden name is a string, so we do not need `int()`

so the solution is:

```python
def ft_garden_name():
    a = input("Enter garden name: ")
    print(f"Garden: {a}")
    print("Status: Growing well!")
```

what is the `f` that i put before the `""` in print?

it is called an **f-string**

it lets you put the value of a variable inside a string by writing the variable between `{}`

for example:

```python
print(f"Garden: {a}")
```

---

# **ex2**

now ex2 wants us to calculate the area of a plot

we need to ask the user for the length and the width

because we want to multiply the values, we use `int(input())`

the function should look like this:

```python
def ft_plot_area():
    length = int(input("Enter length: "))
    width = int(input("Enter width: "))
    print(f"Plot area: {length * width}")
```

the `*` symbol means multiplication

so if the length is 5 and the width is 3:

```text
5 * 3 = 15
```

---

# **ex3**

in ex3 there is nothing really new

we ask the user for the harvest of 3 days and then add them together

it should look like this:

```python
def ft_harvest_total():
    day1 = int(input("Day 1 harvest: "))
    day2 = int(input("Day 2 harvest: "))
    day3 = int(input("Day 3 harvest: "))
    print(f"Total harvest: {day1 + day2 + day3}")
```

we use an f-string because we want to print the result of:

```python
day1 + day2 + day3
```

---

# **ex4**

ex4 will now introduce `if` and `else`

so create the function and then do a quick if/else

the exercise says that the plant is ready only if it is strictly more than 60 days old

so the condition is:

```python
age > 60
```

the solution is:

```python
def ft_plant_age():
    age = int(input("Enter plant age in days: "))

    if age > 60:
        print("Plant is ready to harvest!")
    else:
        print("Plant needs more time to grow.")
```

so as you can see, the logic and the syntax are almost the same as in C

the main difference is that python uses indentation instead of brackets

---

# **ex5**

as you can see ex5 is almost the same

it is just another `if/else`

if more than 2 days have passed, we need to water the plants

the solution is:

```python
def ft_water_reminder():
    days = int(input("Days since last watering: "))

    if days > 2:
        print("Water the plants!")
    else:
        print("Plants are fine")
```

btw you might have seen until now that the exercises do not ask you to handle invalid input or negative numbers

you will learn more about handling those cases in later modules because this is just an introduction to python

---

# **ex6**
ok now we are at ex6

here we are asked to create 2 functions:

```python
ft_count_harvest_iterative()
```

and:

```python
ft_count_harvest_recursive()
```

both functions have to give the same output

they ask the user how many days are left until harvest and then print every day starting from 1

for example if the user writes 5, the output should be:

```text
Day 1
Day 2
Day 3
Day 4
Day 5
Harvest time!
```

## iterative version

first we are gonna do the iterative version

iterative means that we solve it by using a loop

first we ask the user for the number of days:

```python
days = int(input("Days until harvest: "))
```

now we use a `for` loop with `range()`

```python
for day in range(1, days + 1):
```

`range()` starts from the first number but stops before the last number

this is why we use `days + 1`

for example:

```python
range(1, 6)
```

gives us:

```text
1 2 3 4 5
```

so the iterative solution is:

```python
def ft_count_harvest_iterative():
    days = int(input("Days until harvest: "))

    for day in range(1, days + 1):
        print(f"Day {day}")

    print("Harvest time!")
```

this function goes inside the file:

```text
ft_count_harvest_iterative.py
```

## recursive version

now we are gonna do the recursive version

recursion means that a function calls itself

first we ask the user for the number of days:

```python
days = int(input("Days until harvest: "))
```

then we create a small helper function inside our function:

```python
def count(day):
```

the helper function prints the current day and then calls itself with the next day:

```python
count(day + 1)
```

but we also need to stop the function

otherwise it would continue calling itself forever

we stop it when `day` becomes bigger than `days`:

```python
if day > days:
    return
```

`return` stops the function

then we start the counting from day 1:

```python
count(1)
```

so the recursive solution is:

```python
def ft_count_harvest_recursive():
    days = int(input("Days until harvest: "))

    def count(day):
        if day > days:
            return

        print(f"Day {day}")
        count(day + 1)

    count(1)
    print("Harvest time!")
```

this function goes inside the file:

```text
ft_count_harvest_recursive.py
```

the iterative and recursive functions produce the same output

the only difference is that the iterative version uses a loop while the recursive version uses a function that calls itself

---

# **ex7**

ok now we are at ex7

here we are asked to create a function named:

```python
ft_seed_inventory()
```

this function is a little different because the values are given directly to the function through parameters

the function has to look exactly like this:

```python
def ft_seed_inventory(
    seed_type: str,
    quantity: int,
    unit: str
) -> None:
```

the things after `:` are called type hints

```python
seed_type: str
```

means that `seed_type` should be a string

```python
quantity: int
```

means that `quantity` should be an integer

```python
unit: str
```

means that `unit` should be a string

and:

```python
-> None
```

means that the function does not return a value

it only prints the result

we do not use `input()` in this exercise because the values are given directly when the function is called

for example:

```python
ft_seed_inventory("tomato", 15, "packets")
```

here:

```python
seed_type = "tomato"
quantity = 15
unit = "packets"
```

the seed name has to start with a capital letter

so we use:

```python
seed_type = seed_type.capitalize()
```

`.capitalize()` changes the first letter into a capital letter

for example:

```text
tomato
```

becomes:

```text
Tomato
```

now we have to check the unit

the units that we can use are:

```text
packets
grams
area
```

so we use `if`, `elif` and `else`

`elif` means else if

if the unit is `packets`, we print that the packets are available

if the unit is `grams`, we print the total grams

if the unit is `area`, we print how many square meters the seeds cover

if the unit is anything else, we print:

```text
Unknown unit type
```

so the solution is:

```python
def ft_seed_inventory(
    seed_type: str,
    quantity: int,
    unit: str
) -> None:
    seed_type = seed_type.capitalize()

    if unit == "packets":
        print(f"{seed_type} seeds: {quantity} packets available")
    elif unit == "grams":
        print(f"{seed_type} seeds: {quantity} grams total")
    elif unit == "area":
        print(f"{seed_type} seeds: covers {quantity} square meters")
    else:
        print("Unknown unit type")
```

this function goes inside the file:

```text
ft_seed_inventory.py
```

example:

```python
ft_seed_inventory("tomato", 15, "packets")
```

output:

```text
Tomato seeds: 15 packets available
```

example:

```python
ft_seed_inventory("carrot", 8, "grams")
```

output:

```text
Carrot seeds: 8 grams total
```

example:

```python
ft_seed_inventory("lettuce", 12, "area")
```

output:

```text
Lettuce seeds: covers 12 square meters
```

and if we give an unknown unit:

```python
ft_seed_inventory("tomato", 10, "boxes")
```

the output is:

```text
Unknown unit type
```

and now you have finished your first python project
