## Python Basics: Variables, Literals and Constants 😎

Howdy, thanks for checking out this Python beginners article! 😃 If you haven't read Part 1 in this series, you can check it out  [here](https://laylacodes.hashnode.dev/python-basics-keywords-identifiers-and-indention)! <br>
<br>
But, if you've already read Part 1... <br>
LET'S GET ROLLIN'! 😛 
<iframe src="https://giphy.com/embed/GS9pfaxQj5hPKFGGp8" width="280" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/theoffice-the-office-tv-promotion-GS9pfaxQj5hPKFGGp8"></a></p>

Check out the Table of Contents below to see what we'll be going over in Part 2 ⬇️ 

### Table of Contents
-  [Variables](#variables) 
-  [Constants](#constants) 
-  [Numeric Literals](#numeric) 
- [String Literals](#string)
- [Boolean Literals](#boolean)
- [Special Literals](#special)


_____
### <a id="variables">Variables</a>

A **variable** is a named location used to store data in memory. Think of variables like a container that holds data and can be changed later in the program. See below ⬇️ 

```python
item = 200
```
Above, I created a variable named `item` and assigned the numerical value of 200 to it!

I usually think of variables as a grocery basket with items inside and any of the items can be replaced *at any time.*

We can easily **rewrite** variable assignments like so ⬇️ 
```python
item = 100
item = 1.1
```
Initially, the variable `item` had a value of 100, but was rewritten to represent the value 1.1

### Assigning Values to Variables 

Declaring and assigning values to variables is *super easy* in Python! Here's an example below ⬇️ 
```python
website = "seymourbutts.com"
print(website)
```
And the **output:**
```python
seymourbutts.com
```
I assigned a value `seymourbutts.com` to the variable `website`. Then, I printed out the value assigned `website` i.e. seymourbutts.com!

Now, if you decide you want to **change the value** of your variable, that is *also* super easy! Check it out ⬇️ 
```python
# assign initial value to website 
website = "seymourbutts.com"
print(website)

# assigning a new value to website
website = "udemy.com"

print(website)
```
And the **output:**
```python
udemy.com
```

But, what if you need to assign *multiple* values to *multiple* variables? Look below ⬇️ 
```python
a, b, c = 10, 12.2, "Howdy"

print (a)
print (b)
print (c)
```
**Output:**
```python
10
12.2
Howdy
```
<iframe src="https://giphy.com/embed/0NwSQpGY6ipgOSt8LL" width="380" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/theoffice-episode-1-the-office-tv-0NwSQpGY6ipgOSt8LL"></a></p>

You an also assign **the same value** to multiple variables! 
```python
d = e = f = "same"

print (d)
print (e)
print (f)
```

**Output:**
```python
same
same
same
```

### <a id="constants">Constants</a>

Constants are a variable, but they **cannot be changed**. Think about constants like your grocery basket of items, it holds your groceries, which can't be replaced! These are perfect for values that need to be referenced in your code, but you don't plan on changing. 😎 

For example, in a grocery list calculator, a constant would be `SALES TAX = 6.25` or in a math calculator program, `PI = 3.14`. Constants are *usually capitalized* to prevent them from getting confused with normal variables.

Here's an example of declaring a constant ⬇️ 
```python
PI = 3.14
```

Now, let's talk about **rules for naming variables & constants!**
- Give constants and variables a combination of letters in lowercase (a to z) or uppercase (A to Z) or digits (0 to 9) or an underscore (_)! 

Like so:
```python
snake_case
MACRO_CASE
camelCase
CapWords
```
- Create a name that makes sense for the program you're creating! Like: `groceries` makes more sense than `g`! 
- Use underscore (_) if you want to create a variable with two or more words! Like: `my_name` or `grocery_list`!
- Use capital letters to declare constants. Like: `GRAVITY = 9.7`
_______

### Literals

Literals are raw data given in a variable or constant. There's numerous types of literals in Python, but don't worry-- we'll break 'em down 😎 

### <a id="numeric">Numeric Literals</a>

Numeric literals are immutable (unchangeable). Numeric literals can belong to 3 different numerical types: `Integer` (whole numbers) , `Float` (decimal numbers), and `Complex` (complex numbers are in the form x + yi).

So, **how do you use numeric literals in Python?** Check it out below ⬇️ 

```python
a = 0b1010 #Binary Literals
b = 1000 #Decimal Literal 
c = 0o310 #Octal Literal
d = 0x12c #Hexadecimal Literal

#Float Literal
float_1 = 10.5 
float_2 = 1.5e2

print(a, b, c, d)
print(float_1, float_2)
```

**Output:**
```python
10 100 200 300
10.5 150.0
```
Breakdown:
- I assigned integer literals into different variables above. In the first block of code, `a` is a binary literal, `b` is a decimal literal, `c` is an octal literal and `d` is a hexadecimal literal.
- In the second block of code commented `#Float Literal`, `10.1` and `1.5e2` are **floating-point literals**. `1.5e2` is expressed with exponential (the `e` stands for exponential) and is equivalent to `1.5 * 102`


### <a id="string">String Literals</a>

A string literal is a line of characters surrounded by quotes. We can use both single, double, or triple quotes for a string. And, a *character literal* is a single character surrounded by single or double quotes!

So.. **how do you use string literals in Python?** Check it out below ⬇️ 
```python
strings = "I love Python"
char = "C"
multiline_str = """This is a multiline string with more than one line of code!"""
unicode = u"\u00dcnic\u00f6de"
raw_str = r"look! it's a \n string"

print(strings)
print(char)
print(multiline_str)
print(unicode)
print(raw_str)
```

**Output:**

```python
I love Python
C
This is a multiline string with more than one line of code!
Ünicöde
look! it's a \n string
```

Alright, here's the **breakdown:**
- `I love Python` is a **string literal** and `C` is a **character literal.**
- The value in triple-quotes """ assigned to the `multiline_str` is a **multi-line string literal.**
- The string `u"\u00dcnic\u00f6de"` is a **Unicode literal** which supports characters other than English. In this case, `\u00dc` represents `Ü` and `\u00f6` represents `ö`.

Hold on, folks...we're *almost* done with Literals! 
<iframe src="https://giphy.com/embed/cXblnKXr2BQOaYnTni" width="380" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/theoffice-the-office-tv-moroccan-christmas-cXblnKXr2BQOaYnTni"></p>

### <a id="boolean">Boolean Literals</a>

These are simple (thank the heavens!): A Boolean literal can have any of the two values, `True` or `False`. 
*Most importantly!* `True` = the value of `1` and `False` = the value of 0.

**How do we use boolean literals in Python?** Check it out ⬇️ 
```python
x = (1 == True)
y = (9 == False)
a = True + 5
b = False + 10

print("x is", x)
print("y is", y)
print("a:", a)
print("b:", b)
```

**Output:**
```python
x is True
y is False
a: 6
b: 10
```

**Breakdown:**
- In the code above, I used a boolean literal `True` and `False`. (Don't forget: in Python, True equals the value 1 and False equals 0.) The value of `x` is `True` because 1 is equal to True. And, the value of `y` is `False` because 1 is not equal to False.

- Similarly, I used `True` and `False` with numeric expressions as their value. The value of `a` is `5` because we add True which has a value of 1 with 4. And `b` is `10` because we add False, which has a value of 0, to 10.

### <a id="special">Special Literals</a>

This one is fun! 😉 Python contains *one special literal* --> `None`. We use it to specify that the field haven't been created yet! Check out an example ⬇️ 
```python
drink = "Available"
appetizer = None

def menu(x):
    if x == drink:
        print(drink)
    else:
        print(appetizer)

menu(drink)
menu(appetizer)
```

**Output:**
```python
Available
None
```
**Breakdown:**
- I defined a `menu` function. Inside `menu`, when we set the argument as drink then, it displays `Available`. And, when `menu()`'s argument is `appetizer`, it displays `None`! 

_____

You're done!! 🎉😆 

<iframe src="https://giphy.com/embed/b5LTssxCLpvVe" width="380" height="260" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/dancing-happy-smiling-b5LTssxCLpvVe"></a></p>

### In Part 3, I'll be going over:
- **All the Python Operators** (arithmetic, logical, assignment operators)
- **Input, Output and Import** (how to take input from the user, save it to a variable, display output, and import other Python modules) 😊 

We're soo close to writing our first block of Python code!!!! Whoooop!! 😎  See you next week ❤️ 

