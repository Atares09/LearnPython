# Introduction to Python using Codecademy

Welcome to guided walkthrough with [Codecademy](https://www.codecademy.com/learn) introduction to Python 2.7 Programming. Please note that the syntax below is for Python 2.7. Guides for Python 3.6.4 will be available in other course summaries. 

## Python learning journal 
### Key rules before embarking ... 
 
### Disabling PyLint  
(select File > Preferences > Settings, then locate Python configuration) and edit this line as "python.linting.pylintEnabled": false 
 
### 1. How to access characters in a string? 
```python
fifth_char = “PYTHON”[4] 
```
### 2. Printing to screen

```python
Hello world:  
print (”Hello world!”) 
``` 
### 3. Comments, single line #, Multiline: “””     comments “”” 
 
### 4. Multiplication: *, exponentiation ** 
 
### 5. Modulo 3 % 2 = 1 (this gives the remainder)  
 
### 6. Key functions for analysing strings 

```python
len(string) 
string.lower() 
string.upper() 
str(non string) 
```

### 7. Dot notation: 
When manipulating text we use the dot notation with reserved word functions. These are 
..* str() 
..* len() 
which work with all data types 

```python 
name = raw_input("What is your name?") 
quest = raw_input("What is your quest?") 
color = raw_input("What is your favorite color?") 
print "Ah, so your name is %s, your quest is %s, " \ 
"and your favorite color is %s." % (name, quest, color) 
```

### 8. How to extract the date using libraries 

```python
From datetime import datetime 
Now = datetime.now() 
Now.month, day, year, hour, minute, second 
```

# Lab exercise 1: Pig Latin converter
```python
def pyglatin(): 
    # variable definitions 
    original = raw_input('Enter your first word to translate:') 
    if (len(original) > 0) and original.isalpha(): 
        print "You typed %s" % (original) 
        pyg = "ay" 
        word = original.lower() 
        first = word[0] 
        newword = original 
        pigword = word[1:len(original)] 
        newword = word[1:len(newword)]+ first + pyg 
        print first 
        print pigword         
        new_word = word[1:len(newword)]+ first + pyg 
        print "The word in piglatin is %s" % (new_word) 
        return True 
    else: 
        print "The word you entered is invalid, please try again" 
        pyglatin() 
     
print 'Welcome to the Pig Latin Translator!' 
pyglatin() 
```
## MIT Solution 
```python 

VOWELS = ('a', 'e', 'i', 'o', 'u') 
def convert_word(word): 
    first_letter = word[0] 
    if first_letter in VOWELS:  # if word starts with a vowel... 
        return word + "hay"     # then keep it as it is and add hay to the end 
    else: 
        return word[1:] + word[0] + "ay"    # like the lab mentions, word[1:] 
                                            # returns the word except word[0] 
# From this function, it's easy to take a sentence and convert it to Pig-Latin. 
def convert_sentence(sentence): 
    list_of_words = sentence.split(' ') 
    new_sentence = ""   # we'll keep concatenating words to this... 
    for word in list_of_words: 
        new_sentence = new_sentence + convert_word(word)    # ...like this 
        new_sentence = new_sentence + " "   # but don't forget the space! 
    return new_sentence 
 # Now, let's write the main program code, to ask the user and convert. 
  
print "Type in a sentence, and it'll get converted to Pig-Latin!" 
print "Please don't use punctuation or numbers." 
print "Also, we can't handle uppercase/lowercase yet, so lowers only please!" 
print 
  
text = raw_input()  # nothing in the parentheses, because there's nothing else 
                    # extra to tell the user before he is allowed to type 
print 
print convert_sentence(text) 
Page Break
 
def shout(phrase): 
    if phrase == phrase.upper(): 
        return "YOU'RE SHOUTING!" 
    else: 
        return "Can you speak up?" 
 
 
print "Checks whether comments are in Caps" 
user_input = raw_input("Enter your comment here ") 
print shout(user_input) 
Page Break
```

### Function to cube a number
```python
def cube(number): 
    number = number**3 
    return number 
def by_three(number): 
    if number % 3 == 0: 
        number = cube(number) 
        return number 
    else: 
        return False 
user_input = raw_input("Enter a number") 
user_input = int(user_input) 
print by_three(user_input) 
Page Break
```

# Importing the math library 
```python
import math 
print math.sqrt(25) 
```
 
# How to import just a function from a library 
Sometimes all the contents of a library aren't required so we may just import a module from within it. The benefits are the speed of loading and executing the code.

e.g. 
```python
From math import sqrt 
```
 
# Import *everything* from the math module on line 3! 
```python
from math import * 
```

# List all functions belonging to a library 
```python
import math            # Imports the math module 
everything = dir(math) # Sets everything to a list of things from math 
print everything       # Prints 'em all! 
```

# Printing basic statistics - largest, smallest & distance from 0
```python
def biggest_number(*args): 
    print max(args) 
    return max(args) 
def smallest_number(*args): 
    print min(args) 
    return min(args) 
 
def distance_from_zero(arg): 
    print abs(arg) 
    return abs(arg) 
biggest_number(-10, -5, 5, 10) 
smallest_number(-10, -5, 5, 10) 
distance_from_zero(-10) 
# Print out the types of an integer, a float, 
# and a string on separate lines below. 
Page Break
print type(42) 
print type(4.2) 
print type('spam') 
```

```python
ef shut_down(s): 
    if s == "yes": 
        return "Shutting down" 
    elif s == "no": 
        return "Shutdown aborted" 
    else: 
        return "Sorry" 
 
 
print "Prepare to Shutdown? " 
option = "no"  
output = shut_down(option) 
print output 
Page Break
```
# Small example of the sqrt function

```python
from math import sqrt  
print sqrt(13689) 
```

# If-Else statements to calculate hotel bookings

```python
# Function definitions 
 
 
def hotel_cost(nights): 
    return 140*nights 
 
 
def plane_ride_cost(city): 
    if city == "Charlotte": 
        return 183 
    elif city == "Tampa": 
        return 220 
    elif city == "Pittsburgh": 
        return 222 
    elif city == "Los Angeles": 
        return 475 
    else: 
        return "City not covered" 
 
 
def rental_car_cost(days): 
    cost = 40 * days 
    if days >= 7: 
        cost -= 50 
    elif days >= 3 and days < 7: 
        cost -= 20 
     
    return cost 
 
 
def trip_cost(city, days, spending_money): 
    total_cost = rental_car_cost(days) + hotel_cost(days) + plane_ride_cost(city) + spending_money 
    return total_cost 
     
print "Trip cost calculator" 
city = raw_input("Which city are you travelling to? ") 
days = int(raw_input("How many days are you travelling for? ")) 
spending_money = int(raw_input("how much spending money do you need? ")) 
print "You are travelling to %s for %d days with %d spending money" % (city, days, spending_money) 
print "Your total trip costs %s" % (trip_cost(city,days, spending_money)) 
```
 
# Conditional Flow notes: 
Logical operators often provide a way to simplify nested conditional statements. For example, we can rewrite the following code using a [single conditional](http://www.openbookproject.net/books/bpp4awd/ch04.html):

```python
if 0 < x:            # assume x is an int here    if x < 10:        print("x is a positive single digit.") 
```
The print function is called only if we make it past both the conditionals, so we can use the and operator: 
```python
if 0 < x and x < 10:    print("x is a positive single digit.") 
```
Python actually allows a short hand form for this, so the following will also work: 
```python
if 0 < x < 10:    print("x is a positive single digit.") 
```
Example: 
```python
def is_numeric(num): 
    if type(num) == int or type(num) == float: 
        return True 
    else: 
        return False 
 
 
def distance_from_zero(args): 
    if is_numeric(args) == True: 
        return abs(args) 
    elif is_numeric(args) == False: 
        return "Nope" 
    else: 
        return "not valid" 
user_input = int(raw_input("Enter a number to determine its absolute value")) 
print "You entered %d" % (user_input) 
print "The abs value is %d" % (distance_from_zero(user_input)) 
```
# For Loops: 
```python
for i in range(5): 
    print('i is now:', i) 
i is now 0 
i is now 1 
i is now 2 
i is now 3 
i is now 4 
```

# Lists 
```python
zoo_animals = ["pangolin", "cassowary", "sloth", "Llama" ]; 
```

# One animal is missing! 
```python
if len(zoo_animals) > 3: 
print "The first animal at the zoo is the " + zoo_animals[0] 
print "The second animal at the zoo is the " + zoo_animals[1] 
print "The third animal at the zoo is the " + zoo_animals[2] 
print "The fourth animal at the zoo is the " + zoo_animals[3] 
```

# Sometimes, you only want to access a portion of a list. 
```python
letters = ['a', 'b', 'c', 'd', 'e'] 
slice = letters[1:3]  
print slice 
print letters 
```

In the above example, we first create a list called letters. 
Then, we take a subsection and store it in the slice list. We start at the index before the colon and continue up to but not including the index after the colon. 

# Slicing Lists and Strings 
You can slice a string exactly like a list! In fact, you can think of strings as lists of characters: each character is a sequential item in the list, starting from index 0. 

```python
my_list[:2]# Grabs the first two itemsmy_list[3:]# Grabs the fourth through last items 
```
If your list slice includes the very first or last item in a list (or a string), the index for that item doesn't have to be included.  

Sometimes you need to search for an item in a list. 
```python
animals = ["ant", "bat", "cat"]
print animals.index("bat") 
```

First, we create a list called animals with three strings. 
Then, we print the first index that contains the string "bat", which will print 1. 
We can also insert items into a list. 

```python
animals.insert(1, "dog")print animals 
```
We insert "dog" at index 1, which moves everything down by 1. 
We print out ["ant", "dog", "bat", "cat"] 

 
# How to Append: 

```python
suitcase = []  
suitcase.append("sunglasses") 
suitcase.append("T-shirt") 
suitcase.append("boardshorts") 
suitcase.append("sunscreen") 
list_length = len(suitcase) # Set this to the length of suitcase 
print "There are %d items in the suitcase." % (list_length) 
print suitcase 
```
 
# For One and All 
If you want to do something with every item in the list, you can use a for loop. If you've learned about for loops in JavaScript, pay close attention! They're different in Python. 
for variable in list_name:    # Do stuff! 
A variable name follows the for keyword; it will be assigned the value of each list item in turn. 
Then in list_name designates list_name as the list the loop will work on. The line ends with a colon (:) and the indented code that follows it will be executed once per item in the list. 
Example: 
```python
my_list = [1,9,3,8,5,7] 
for number in my_list: 
    print 2*number 
```
```python 
start_list = [5, 3, 1, 2, 4] 
square_list = [] 
 
for number in start_list: 
    square_list.append(number**2) 
square_list.sort() 
print square_list 
 
```
 
# Dictionary entries 
```python
menu = {} # Empty dictionary 
menu['Chicken Alfredo'] = 14.50 # Adding new key-value pair 
menu['Chicken parmaganna'] = 9.50 
menu['Spaghetti Bolognese'] = 10.50 
menu['Quesadilla'] = 6.50 
 
 
print "There are " + str(len(menu)) + " items on the menu." 
print menu 
```
 
## Adding and removing entries from a dictionary entry 
```python
# key - animal_name : value - location  
zoo_animals = { 'Unicorn' : 'Cotton Candy House', 
'Sloth' : 'Rainforest Exhibit', 
'Bengal Tiger' : 'Jungle House', 
'Atlantic Puffin' : 'Arctic Exhibit', 
'Rockhopper Penguin' : 'Arctic Exhibit'} 
```

# A dictionary (or list) declaration may break across multiple lines 
Removing the 'Unicorn' entry. (Unicorns are incredibly expensive.) 
```python
del zoo_animals['Unicorn'] 
# Your code here! 
del zoo_animals['Sloth'] 
del zoo_animals['Bengal Tiger'] 
zoo_animals['Rockhopper Penguin'] = 'Jungle House' 
print zoo_animals 
```
 
| Escape Sequence | Meaning                        |
|-----------------|--------------------------------|
| \newline        | Backslash and newline ignored  |
| \\              | Backslash                      |
| \'              | Single quote (')               |
| \"              | Double quote (")               |
| \a              | ASCII Bell (BEL)               |
| \b              | ASCII Backspace (BS)           |
| \f              | ASCII Formfeed (FF)            |
| \n              | ASCII Linefeed (LF)            |
| \r              | ASCII Carriage Return (CR)     |
| \t              | ASCII Horizontal Tab (TAB)     |
| \v              | ASCII Vertical Tab (VT)        |
| \ooo            | Character with octal value ooo |
| \xhh            | Character with hex value hh    |
|                 |                                |
 
Python allows for strings to be defined with either single or double quotes 
Page Break
 
# How to remove list items: 
```python
backpack = ['xylophone', 'dagger', 'tent', 'bread loaf'] 
backpack.remove('dagger') 
```
```python 
Comment all highlighted text 
Ctrl + / 
```
 
### Further details with dictionaries 
You can store a list, number or a string as an associated variable to a key 
```python
my_dict = { 
    "fish": ["c", "a", "r", "p"], 
    "cash": -4483, 
    "luck": "good" 
} 
print my_dict["fish"][0:4] 
Prints out:  ["c", "a", "r", "p"] 
```
 
### Adding and removing dictionary entries 
```python
inventory = { 
    'gold' : 500, 
    'pouch' : ['flint', 'twine', 'gemstone'], # Assigned a new list to 'pouch' key 
    'backpack' : ['xylophone','dagger', 'bedroll','bread loaf'] 
} 
 
# Adding a key 'burlap bag' and assigning a list to it 
inventory['burlap bag'] = ['apple', 'small ruby', 'three-toed sloth'] 
# Sorting the list found under the key 'pouch' 
inventory['pouch'].sort()  
# Your code here 
inventory['pocket'] = ['seashell', 'strange berry', 'lint'] 
inventory['backpack'].sort() 
inventory['backpack'].remove('dagger') 
inventory['gold'] += 50 
print inventory 
```

### Printing multiple dictionaries using for loops 
```python
prices = {"banana": 4, "apple": 2, "orange": 1.5, "pear": 3} 
stock = {"banana": 6, "apple": 0, "orange": 32, "pear": 15} 
for products in prices: 
    print products 
    print "price: %s" % prices[products] 
    print "stock: %s" % stock[products] 
```

### Printing and adding to dictionary values 
```python
prices = { 
    "banana" : 4, 
    "apple" : 2, 
    "orange" : 1.5, 
    "pear" : 3, 
} 
stock = { 
    "banana" : 6, 
    "apple" : 0, 
    "orange" : 32, 
    "pear" : 15, 
} 
 
for key in prices: 
    print key 
    print "price: %s" % prices[key] 
    print "stock: %s" % stock[key] 
 
total = 0 
for key in prices: 
    total = total + prices[key]*stock[key]  
print total 
```

# Using Dictionaries and lists to calculate the price of a shopping list 
```python 
shopping_list = ["banana", "orange", "apple"] 
 
 
stock = { 
    "banana": 6, 
    "apple": 0, 
    "orange": 32, 
    "pear": 15 
} 
     
prices = { 
    "banana": 4, 
    "apple": 2, 
    "orange": 1.5, 
    "pear": 3 
} 
 
 
def compute_bill(food): 
    total = 0 
    for key in food: 
        total += prices[key] 
    return total 
     
print compute_bill(shopping_list) 
 
```
```python 
shopping_list = ["banana", "orange", "apple"] 
 
stock = { 
    "banana": 6, 
    "apple": 0, 
    "orange": 32, 
    "pear": 15 
} 
     
prices = { 
    "banana": 4, 
    "apple": 2, 
    "orange": 1.5, 
    "pear": 3 
} 
# Write your code below! 
 
def compute_bill(food): 
    total = 0 
 
    for key in food: 
        if stock[key] > 0: 
            total += prices[key] 
            stock[key] = stock[key]-1 
    print stock 
    return total 
 
print "Your total comes out to: $%s" % (compute_bill(shopping_list)) 
 
```

### Printing items in stock referencing both key and stock items: 
```python
shopping_list = ["banana", "orange", "apple"] 

stock = { 
    "banana": 6, 
    "apple": 0, 
    "orange": 32, 
    "pear": 15 
} 
     
prices = { 
    "banana": 4, 
    "apple": 2, 
    "orange": 1.5, 
    "pear": 3 
} 
 
# Write your code below! 
 
def compute_bill(food): 
    total = 0 
    for key in food: 
        if stock[key] > 0: 
            total += prices[key] 
            stock[key] = stock[key]-1 
    return total 
 
print "Your total comes out to: $%s" % (compute_bill(shopping_list)) 
 
print "Remaining stock items are:" 
for keys in stock: 
    print "%s : %s"% (keys, stock[keys]) 
```
```python 
shopping_list = ["banana", "orange", "apple"] 
 
stock = { 
    "banana": 6, 
    "apple": 0, 
    "orange": 32, 
    "pear": 15 
} 
     
prices = { 
    "banana": 4, 
    "apple": 2, 
    "orange": 1.5, 
    "pear": 3 
} 
 
# Write your code below! 
 
def compute_bill(food): 
    total = 0 
 
    for key in food: 
        if stock[key] > 0: 
            total += prices[key] 
            stock[key] = stock[key]-1 
    return total 
 
print "Your shopping list is %s" % (shopping_list) 
print "items in stock are are:" 
for keys in stock: 
    print "%s : %s"% (keys, stock[keys]) 
 
print "Your total comes out to: $%s" % (compute_bill(shopping_list)) 
 
print "Remaining stock items are:" 
for keys in stock: 
    print "%s : %s"% (keys, stock[keys]) 
     
 
 
```
# Homework grading
```python
lloyd = { 
    "name": "Lloyd", 
    "homework": [90.0, 97.0, 75.0, 92.0], 
    "quizzes": [88.0, 40.0, 94.0], 
    "tests": [75.0, 90.0] 
} 
alice = { 
    "name": "Alice", 
    "homework": [100.0, 92.0, 98.0, 100.0], 
    "quizzes": [82.0, 83.0, 91.0], 
    "tests": [89.0, 97.0] 
} 
tyler = { 
    "name": "Tyler", 
    "homework": [0.0, 87.0, 75.0, 22.0], 
    "quizzes": [0.0, 75.0, 78.0], 
    "tests": [100.0, 100.0] 
} 
 
 
# Add your function below! 
def average(numbers): 
    total = 0 
    total = float(sum(numbers))/len(numbers) 
    return total 
 
 
def get_average(student): 
    homework = average(student["homework"]) 
    quizzes = average(student["quizzes"]) 
    tests = average(student["tests"]) 
    return 0.1*homework + 0.3*quizzes + 0.6*tests 
     
def get_letter_grade(score): 
    if score >= 90: 
        return "A" 
    elif score >= 80: 
        return "B" 
    elif score >= 70: 
        return "C" 
    elif score >= 60: 
        return "D" 
    else: 
        return "F" 
         
def get_class_average(students): 
    results = [] 
    for student in students: 
        results.append(get_average(student)) 
    return average(results) 
 
 
students = [lloyd, alice, tyler] 
 
 
print get_class_average(students) 
print get_letter_grade(get_class_average(students)) 
```     
 
 
# How to append to a list 
```python 
n = [1, 3, 5] 
# Append the number 4 here 
n.append(4) 
 print n 
Page Break
Removing elements from lists 
This exercise will expand on ways to remove items from a list. You actually have a few options. For a list called n: 
n.pop(index) will remove the item at index from the list and return it to you: 
n = [1, 3, 5]n.pop(1)# Returns 3 (the item at index 1)print n# prints [1, 5] 
n.remove(item) will remove the actual item if it finds it: 
n.remove(1)# Removes 1 from the list,# NOT the item at index 1print n# prints [3, 5] 
del(n[1]) is like .pop in that it will remove the item at the given index, but it won't return it: 
del(n[1])# Doesn't return anythingprint n# prints [1, 5] 
Example: 
n = [1, 3, 5] 
# Remove the first item in the list here 
 # del(n[0]) 
# n.pop(0) 
# n.remove(1) 
 print n 
```

```python
# Manipulating Functions 
 
m = 5 
n = 13 
# Add add_function here! 
def add_function(x, y): 
    return x + y 
 print add_function(m, n) 
  
```
 
### Concatenating string functions 

```python
n = "Hello" 
# Your function here! 
def string_function(s): 
    return s +" "+ "world" 
 print string_function(n) 
```

```python
Passing a list to a function 
You pass a list to a function the same way you pass any other argument to a function. 
def list_function(x): 
    return x 
 n = [3, 5, 7] 
print list_function(n) 
```
 
# Using an element from a list in a function 
Passing a list to a function will store it in the argument (just like with a string or a number!) 
```python
def first_item(items):    print items[0]numbers = [2, 7, 9]first_item(numbers) 
```
In the example above, we define a function called first_item. It has one argument called items. 

Inside the function, we print out the item stored at index zero of items. 

After the function, we create a new list called numbers. 

Finally, we call the first_itemfunction with numbers as its argument, which prints out 2. 
```python
def list_function(x): 
    return x[1] 
 n = [3, 5, 7] 
print list_function(n) 
```
 
# Modifying an element of a list in a function 

Modifying an element in a list in a function is the same as if you were just modifying an element of a list outside a function. 
```python
def double_first(n):    n[0] = n[0] * 2numbers = [1, 2, 3, 4]double_first(numbers)print numbers 
```

We create a list called numbers. 
We use the double_first function to modify that list. 
Finally, we print out [2, 2, 3, 4] 

When we pass a list to a function and modify that list, like in the double_first function above, we end up modifying the original list. 
```python
def list_function(x): 
     
    x[1] = x[1] + 3 
     
    return x 
  
n = [3, 5, 7] 
  
print list_function(n) 
 
```
 
# Printing out a list item by item in a function 
This exercise is to go over how to utilize every element in a list in a function. You can use the existing code to complete the exercise and see how running this operation inside a function isn't much different from running this operation outside a function. 

Don't worry about the range function quite yet—we'll explain it later in this section. 

```python
n = [3, 5, 7] 
for i in range(0, len(n)): 
    print n[i] 
 
Or... 
n = [3, 5, 7] 
def print_list(x): 
    for i in range(0, len(x)): 
        print x[i] 
 print_list(n) 
```
```python 
n = [3, 5, 7] 
  
def double_list(x): 
    for i in range(0, len(x)): 
        x[i] = x[i] * 2 
    return x 
# Don't forget to return your new list! 
  
print double_list(n) 
```
 
# Passing a range into a function 
Okay! Range time. The Python range()function is just a shortcut for generating a list, so you can use ranges in all the same places you can use lists. 

```python
range(6) # => [0,1,2,3,4,5]
range(1,6) # => [1,2,3,4,5]
range(1,6,3) # => [1,4] 
```

### The range function has three different versions: 
```python
range(stop) 
range(start, stop) 
range(start, stop, step) 
```
In all cases, the range() function returns a list of numbers from start up to (but not including) stop. Each item increases by step. 
If omitted, start defaults to zero and step defaults to one. 

### Using strings in lists in functions 

Now let's try working with strings! 

for item in list:    print itemfor i in range(len(list)):    print list[i] 

The example above is just a reminder of the two methods for iterating over a list. 

### Instructions 
Create a function that concatenates strings. 
Define a function called join_strings accepts an argument called words. It will be a list. 
Inside the function, create a variable called result and set it to "", an empty string. 
Iterate through the words list and append each word to result. 
Finally, return the result. 
Don't add spaces between the joined strings! 

```python
n = ["Michael ", "Lieberman"] 
# Add your function here 
def join_strings(words): 
    result = "" 
    for item in range(len(words)): 
        result += words[item] 
return result 
 print join_strings(n) 
```

# Using two lists as two arguments in a function 
Using multiple lists in a function is no different from just using multiple arguments in a function! 

```python
a = [1, 2, 3]b = [4, 5, 6]print a + b# prints [1, 2, 3, 4, 5, 6] 
```

The example above is just a reminder of how to concatenate two lists. 
Instructions 
Create a function that joins two lists together. 
On line 4, define a function called join_lists that has two arguments, xand y. They will both be lists. 
Inside that function, return the result of concatenating x and ytogether. 

m = [1, 2, 3] 
n = [4, 5, 6] 
```python
# Add your code here! 
def join_lists(x, y): 
    return x + y 
print join_lists(m, n) 
# You want this to print [1, 2, 3, 4, 5, 6] 
```

### Using a list of lists in a function 

Finally, this exercise shows how to make use of a single list that contains multiple lists and how to use them in a function. 

```python
list_of_lists = [[1,2,3], [4,5,6]]for lst in list_of_lists:    for item in lst:        print item 
```
In the example above, we first create a list containing two items, each of which is a list of numbers. 

Then, we iterate through our outer list. 

For each of the two inner lists (as lst), we iterate through the numbers (as item) and print them out. 

We end up printing out: 

123456 

# Flatten & Concatenate

Create a function called flatten that takes a single list and concatenates all the sublists that are part of it into a single list. 
On line 3, define a function called flatten with one argument called lists. 
Make a new, empty list called results. 
Iterate through lists. Call the looping variable numbers. 
Iterate through numbers. 
For each number, .append() it to results. 
Finally, return results from your function. 
n = [[1, 2, 3], [4, 5, 6, 7, 8, 9]] 

```python
# Add your function here 
def flatten(lists): 
    results = [] 
    for item in lists: 
        for i in item: 
            results.append(i) 
    return results 
 print flatten(n) 
```python

# Project 1: Battle Ship!

## Welcome to Battleship! 
In this project you will build a simplified, one-player version of the classic board game Battleship! In this version of the game, there will be a single ship hidden in a random location on a 5x5 grid. The player will have 10 guesses to try to sink the ship. 

To build this game we will use our knowledge of lists, conditionals and functions in Python. When you're ready to get started, click 
run to continue. 

### Instructions 

Make a List 
Good! Now we'll use a built-in Python function to generate our board, which we'll make into a 5 x 5 grid of all "O"s, for "ocean." 

print ["O"] * 5 

will print out ['O', 'O', 'O', 'O', 'O'], which is the basis for a row of our board. 

We'll do this five times to make five rows. (Since we have to do this five times, it sounds like a loop might be in order.) 

Instructions 
Create a 5 x 5 grid initialized to all 'O's and store it in board. 
Use range() to loop 5 times. 

Inside the loop, .append() a list containing 5 "O"s to board, just like in the example above. 
Note that these are capital letter "O" and not zeros. 
Hide... 

Excellent! Now, let's hide our battleship in a random location on the board. 

Since we have a 2-dimensional list, we'll use two variables to store the ship's location, ship_row and ship_col. 
from random import randintcoin = randint(0, 1)dice = randint(1, 6) 
In the above example, we first import the randint(low, high) function from the random module. 

Then, we generate either zero or one and store it in coin. 
Finally, we generate a number from one to six inclusive. 

Let's generate a random_row and random_col from zero to four! 
```python
from random import randint  
  
board = [] 
 for x in range(0, 5): 
    board.append(["O"] * 5) 
def print_board(board): 
    for row in board: 
        print " ".join(row) 
```       
Okay—now for the fun! We have the actual location of the ship and the player's guess so we can check to see if the player guessed right. 

For a guess to be right, guess_colshould be equal to ship_col and guess_row should be equal to ship_row. 
if guess_col == 0 and guess_row == 0:    print "Top-left corner." 

The example above is just a reminder about if statements. 
Instructions 

On line 29, add an if guess_rowequals ship_row and guess_col equals ship_col. 

If that is the case, please print out "Congratulations! You sank my battleship!" 
You win! 

Okay—now for the fun! We have the actual location of the ship and the player's guess so we can check to see if the player guessed right. 

For a guess to be right, guess_colshould be equal to ship_col and guess_row should be equal to ship_row. 
if guess_col == 0 and guess_row == 0:    print "Top-left corner." 

The example above is just a reminder about if statements. 

Instructions 

On line 29, add an if guess_rowequals ship_row and guess_col equals ship_col. 

If that is the case, please print out "Congratulations! You sank my battleship!" 

## Full code solution:

```python
from random import randint

board = []

for x in range(5):
  board.append(["O"] * 5)

def print_board(board):
  for row in board:
    print " ".join(row)

print_board(board)

def random_row(board):
  return randint(0, len(board) - 1)

def random_col(board):
  return randint(0, len(board[0]) - 1)

ship_row = random_row(board)
ship_col = random_col(board)
print ship_row
print ship_col

# Everything from here on should go in your for loop!
# Be sure to indent four spaces!
guess_row = int(raw_input("Guess Row: "))
guess_col = int(raw_input("Guess Col: "))

if guess_row == ship_row and guess_col == ship_col:
  print "Congratulations! You sunk my battleship!"
else:
  if (guess_row < 0 or guess_row > 4) or (guess_col < 0 or guess_col > 4):
    print "Oops, that's not even in the ocean."
  elif(board[guess_row][guess_col] == "X"):
    print "You guessed that one already."
  else:
    print "You missed my battleship!"
    board[guess_row][guess_col] = "X"
  # Print (turn + 1) here!
  print_board(board)
  ```

### While you're here 

The while loop is similar to an ifstatement: it executes the code inside of it if some condition is true. The difference is that the while loop will continue to execute as long as the condition is true. In other words, instead of executing if something is true, it executes while that thing is true. 

Line 6 decides when the loop will be executed. So, "as long as count is less than 5," the loop will continue to execute. Line 8 increases count by 1. This happens over and over until countequals 5. 

### Instructions 

Change the loop so it counts up to 9 (inclusive). 
Be careful not to change or remove the count += 1. If Python has no way to increase count, your loop could go on forever and become an infinite loopwhich could crash your computer / browser! 
```python
count = 0 
 if count < 5: 
    print "Hello, I am an if statement and count is", count 
    
while count < 5: 
    print "Hello, I am a while and count is", count 
    count += 1 
``` 
Output: 
Hello, I am an if statement and count is 0
Hello, I am a while and count is 0 
Hello, I am a while and count is 1 
Hello, I am a while and count is 2 
Hello, I am a while and count is 3 
Hello, I am a while and count is 4 

 
### While you're here 

The while loop is similar to an ifstatement: it executes the code inside of it if some condition is true. The difference is that the while loop will continue to execute as long as the condition is true. In other words, instead of executing if something is true, it executes while that thing is true. 

Line 6 decides when the loop will be executed. So, "as long as count is less than 5," the loop will continue to execute. Line 8 increases count by 1. This happens over and over until countequals 5. 
Instructions 

Change the loop so it counts up to 9 (inclusive). 
Be careful not to change or remove the count += 1 bit—if Python has no way to increase count, your loop could go on forever and become an infinite loop which could crash your computer / browser! 
 
While you're at it 
Inside a while loop, you can do anything you could do elsewhere, including arithmetic operations. 

### Instructions 

Create a while loop that prints out all the numbers from 1 to 10 squared (1, 4, 9, 16, ... , 100), each on their own line. 
Fill in the blank space so that our while loop goes from 1 to 10 inclusive. 
Inside the loop, print the value of num squared. The syntax for squaring a number is num ** 2. 
Increment num. 
num = 1 
  
while num < 11:   
    print num ** 2 
    num += 1 
149162536496481100 
 
# Simple errors with While Loops 

A common application of a while loop is to check user input to see if it is valid. For example, if you ask the user to enter y or n and they instead enter 7, then you should re-prompt them for input. 
Instructions 

Fill in the loop condition so the user will be prompted for a choice over and over while choice does not equal 'y' and choice does not equal 'n'.Remember, use the != operator to test if two things are different, such as choice != y, and the andoperator to check more than one thing, such as A and B. 

```python
choice = raw_input('Enjoying the course? (y/n)') 
  
while choice != "y" and choice != "n":   
    # Fill in the condition (before the colon) 
    choice = raw_input("Sorry, I didn't catch that. Enter again: ") 
```

# Infinite loops 
An infinite loop is a loop that never exits. This can happen for a few reasons: 

The loop condition cannot possibly be false (e.g. while 1 != 2) 

The logic of the loop prevents the loop condition from becoming false. 

Example: 
```python
count = 10
while count > 0: count += 1 # Instead of count -= 1 
```

Instructions 
The loop in the editor has two problems: it's missing a colon (a syntax error) and count is never incremented (logical error). The latter will result in an infinite loop, so be sure to fix both before running! Since count is never incremented (count += 1), count is always 0, and since 0 < 10, 0 will be printed over and over again forever. 
```python
count = 0 
while count < 10: # Add a colon 
    print count 
    count += 1  
    # Increment count 
Break 
```

The break is a one-line statement that means "exit the current loop." An alternate way to make our counting loop exit and stop executing is with the break statement. 

First, create a while with a condition that is always true. The simplest way is shown. 
Using an if statement, you define the stopping condition. Inside the if, you write break, meaning "exit the loop." 
The difference here is that this loop is guaranteed to run at least once. 

Instructions 
See what the break does? Feel free to mess around with it (but make sure you don't cause an infinite loop)! Click Save & Submit Code when you're ready to continue. 
```python
count = 0 
 while True: 
    print count 
    count += 1 
    if count >= 10: 
        Break 
```

# While / else 
Something completely different about Python is the while/else construction. while/else is similar to if/else, but there is a difference: the else block will execute anytime the loop condition is evaluated to False. This means that it will execute if the loop is never entered or if the loop exits normally. If the loop exits as the result of a break, the elsewill not be executed. 
In this example, the loop will break if a 5 is generated, and the else will not execute. Otherwise, after 3 numbers are generated, the loop condition will become false and the else will execute. 
Instructions 
Click Save & Submit Code to see while/else in action! 

```python
import random 
print "Lucky Numbers! 3 numbers will be generated." 
print "If one of them is a '5', you lose!" 
count = 0 
while count < 3: 
    num = random.randint(1, 6) 
    print num 
    if num == 5: 
        print "Sorry, you lose!" 
        break 
    count += 1 
else: 
    print "You win!" 
```

# Your own while / else 
Now you should be able to make a game similar to the one in the last exercise. The code from the last exercise is below: 
```python
count = 0
while count < 3: 
 num = random.randint(1, 6)    

print num    
if num == 5:  
   print "Sorry, you lose!"
   break    
   count += 1
else:
   print "You win!" 
```

In this exercise, allow the user to guess what the number is three times. 
```python
guess = int(raw_input("Your guess: ")) 
```
Remember, raw_input turns user input into a string, so we use int() to make it a number again. 

### Instructions 

Use a while loop to let the user keep guessing so long as guesses_leftis greater than zero. 

Ask the user for their guess, just like the second example above. 

If they guess correctly, print 'You win!' and break. 

Decrement guesses_left by one. 
Use an else: case after your whileloop to print You lose.. 

This game will have a very similar structure, but instead of losing right before the break, the user should win. 

The if should check if guess == random_number. If it does, then it's the winning guess! 
from random import randint 
  
# Generates a number from 1 through 10 inclusive 
random_number = randint(1, 10) 
  
guesses_left = 3 

# Start your game! 
```python
while guesses_left != 0 : 
    guess = int(raw_input("Your guess: ")) 
    if guess == random_number: 
        print "you win, the number was %d" % (guess) 
        break 
    guesses_left -= 1 
else:  
    print ("You lose, number was %d") % (random_number) 
```
For your health 
An alternative way to loop is the forloop. The syntax is as shown; this example means "for each number i in the range 0 - 9, print i". 

Instructions 
Make the loop print the numbers from 0 to 19 instead of 0 to 9. 
Make sure to change the number inside of range. 
```python
print "Counting..." 
  
for i in range(20): 
    print I 
``` 
### For your hobbies 
This kind of loop is useful when you want to do something a certain number of times, such as append something to the end of a list. 
Instructions 
Create a for loop that prompts the user for a hobby 3 times, then appends each one to hobbies. 
Your for loop should use range(3). You should use the raw_input()function to get info from the user and hobbies.append(hobby) to add the hobby to the list. 
```python
hobbies = [] 
# Add your code below! 
for i in range(5): 
    next_hobby = raw_input("Please enter your hobbies") 
    hobbies.append(next_hobby) 
     
print ("\nYour hobbies are ...\n") 
for i in range(len(hobbies)): 
    print hobbies[i] 
 
```

### For your strings 
Using a for loop, you can print out each individual character in a string. 
The example in the editor is almost plain English: "for each character c in thing, print c". 
Instructions 
Add a second for loop so that each character in word is printed one at a time. 
Use the example on lines 3 - 4 as a model. 
```python 
thing = "spam!" 
 for c in thing: 
    print c 
word = "eggs!" 
for i in word: 
    print i 
```python

String manipulation is useful in forloops if you want to modify some content in a string. 
```python
word = "Marble"
for char in word:    
   print char, 
```

The example above iterates through each character in word and, in the end, prints out M a r b l e. 
The , character after our printstatement means that our next printstatement keeps printing on the same line. 
Instructions 
Let's filter out the letter 'A' from our string. 
Do the following for each character in the phrase. 
If char is an 'A' or char is an 'a', print 'X', instead of char. Make sure to include the trailing comma. 
Otherwise (else:), please printchar, with the trailing comma. 
? 
Hint 
You can use the same for syntax, for c in s, as before. Use an if to compare c to 'a' and 'A'. Print an 'X' in that case, and use an else to print the character otherwise. 
Include a comma after the character to be printed in order to ensure it's not printed on its own line, like so: 
if c == "A" or c == "a":    print "X", 
phrase = "A bird in the hand..." 
  
# Add your for loop 
```python  
for char in phrase: 
    if(char == 'A' or char == 'a'): 
        print 'X', 
    else: 
        print char, 
#Don't delete this print statement! 
Print 
```  

### For your lists 

Perhaps the most useful (and most common) use of for loops is to go through a list. 
On each iteration, the variable num will be the next value in the list. So, the first time through, it will be 7, the second time it will be 9, then 12, 54, 99, and then the loop will exit when there are no more values in the list. 

Instructions 
Write a second for loop that goes through the numbers list and prints each element squared, each on its own line.Use the ** operator for exponentiation. The rest of the loop should be very similar to the first one. 
numbers  = [7, 9, 12, 54, 99] 
```python
print "This list contains: " 
for num in numbers: 
    print num 
# Add your loop below! 
print "The squared list contains:" 
for num in numbers: 
    print num ** 2 
```

### Looping over a dictionary 
You may be wondering how looping over a dictionary would work. Would you get the key or the value? 
The short answer is: you get the key which you can use to get the value. 
```python
d = {'x': 9, 'y': 10, 'z': 20}for key in d:    if d[key] == 10:        print "This dictionary has the value 10!" 
```
First, we create a dictionary with strings as the keys and numbers as the values. 
Then, we iterate through the dictionary, each time storing the key in key. 
Next, we check if that key's value is equal to 10. 
Finally, we print This dictionary has the value 10! 

Instructions 
On line 5, print the key, followed by a space, followed by the value associated with that key. 
An easy way to print in the requested format is to use the , character, like so: 
```python
greeting = "Hello"name = "World"print greeting, name# prints "Hello World" 
d = {'a': 'apple', 'b': 'berry', 'c': 'cherry'} 
  
for key in d: 
    # Your code here! 
    print "%s %s" % (key, d[key]) 
```

### Counting as you go 
A weakness of using this for-each style of iteration is that you don't know the index of the thing you're looking at. Generally this isn't an issue, but at times it is useful to know how far into the list you are. Thankfully the built-in enumerate function helps with this. 

enumerate works by supplying a corresponding index to each element in the list that you pass it. Each time you go through the loop, index will be one greater, and item will be the next item in the sequence. It's very similar to using a normal for loop with a list, except this gives us an easy way to count how many items we've seen so far. 

Instructions 

We don't want the user to see things listed from index 0, since this looks unnatural. Instead, the items should appear to start at index 1. Modify the print statement to reflect this behavior. See the Hint for help. 
Instead of just printing index, print index+1! 
```python
choices = ['pizza', 'pasta', 'salad', 'nachos'] 

print 'Your choices are:' 

for index, item in enumerate(choices): 
    print index+1, itemz 
```

### Multiple lists 
It's also common to need to iterate over two lists at once. This is where the built-in zip function comes in handy. 
zip will create pairs of elements when passed two lists, and will stop at the end of the shorter list. 
zip can handle three or more lists as well! 
Instructions 
Compare each pair of elements and print the larger of the two. 
a is an element from list_a and bis an element of list_b. Use an ifstatement to compare the two and print whichever is larger. 
```python 
list_a = [3, 9, 17, 15, 19] 
list_b = [2, 4, 8, 10, 30, 40, 50, 60, 70, 80, 90] 
for a, b in zip(list_a, list_b): 
    if a > b: 
        print a 
    elif b > a: 
        print b 
``` 

# For / else 
Just like with while, for loops may have an else associated with them. 
In this case, the else statement is executed after the for, but only if the for ends normally—that is, not with a break. This code will break when it hits 'tomato', so the else block won't be executed. 
```python
fruits = ['banana', 'apple', 'orange', 'pear', 'grape'] 
print 'You have...' 
for f in fruits: 
    if f == 'tomato': 
        print 'A tomato is not a fruit!' # (It actually is.) 
        break 
    print 'A', f 
else: 
    print 'A fine selection of fruits!' 
```

### The sum of scores 
Now that we have a function to print the grades, let's create another function to compute the sum of all of the test grades. 
This will be super-helpful when we need to compute the average score. 
I know what you're thinking, "let's just use the built-in sum() function!" The built-in function would work beautifully, but it would be too easy. 


Computing the sum manually involves computing a rolling sum. As you loop through the list, add the current grade to a variable that keeps track of the total, let's call that variable total. 
Instructions 


On line 3, define a function grades_sum() that does the following: 

* Takes in a list of scores, scores 
* Computes the sum of the scores 
* Returns the computed sum 


Call the newly created grades_sum()function with the list of grades and print the result. 
To compute a rolling sum, create a variable total that's initialized to zero. Then, as you loop through the list of grades, add the current grade to total. 
Don't use sum as a variable name as it has a special meaning in Python! 
```python
grades = [100, 100, 90, 40, 80, 100, 85, 70, 90, 65, 90, 85, 50.5] 
  
def print_grades(grades): 
    for grade in grades: 
        print grade 
  
def grades_sum(grades): 
    total = 0 
    for grade in grades:  
        total += grade 
    return total 
     
def grades_average(grades): 
    sum_of_grades = grades_sum(grades) 
    avg = sum_of_grades / float(len(grades)) 
    return avg 
  
def grades_variance(scores): 
    average = grades_average(scores) 
    variance = 0 
    for score in scores: 
        variance += (average - score) ** 2 
    return variance/ float(len(scores)) 
     
def grades_std_deviation(variance): 
    return variance ** 0.5 
  
variance = grades_variance(grades) 
print "Variance %d" % (variance) 
print grades_std_deviation(variance) 
```
