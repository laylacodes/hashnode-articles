## Python Basics: Keywords, Identifiers and Indention 😊

Welcome to the **first article** in my *first series ever:* ** "Python: Explain Like I'm Five"**! 

In this first article, I'll be introducing you to a few beginner Python concepts! 😊 

- reserved keywords
- identifiers & the rules for creating them
- comments
- indention

Strap in, folks. Keep all hands, feet, arms, legs inside the ride. We're about to learn some Python 😎 


<iframe src="https://giphy.com/embed/oF5oUYTOhvFnO" width="280" height="157" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/spongebob-spongebob-squarepants-nickelodeon-oF5oUYTOhvFnO"></a></p>

### Contents 

- ####  [Keywords](#keywords) 
- #### [Identifiers](#identifiers) 
- #### [Statements](#statements) 
- #### [Comments](#commentz) 
- #### [Indention](#indention)

____

### <a id="keywords">Keywords</a>

Keywords are the *reserved words* in Python. We **can't **use these keywords as identifiers (variable names), function names, etc.! They're used to define the syntax & structure of Python. (**Watch out-- they're case-sensitive! Notice how only True, None and False are capitalized!**)

There are 33 keywords in Python! To access these keywords in your Python shell, simply type 
`help> keywords` and they'll pop up! Check 'em out below 😊 

![python keywords (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628721264342/6BDKmab_U.png)
_______
### <a id="identifiers">Identifiers </a>

A Python identifier is a name used to identify a variable, function, class, module or other object. 😎 
<iframe src="https://giphy.com/embed/BCDXLMoKKjyeDXNyLg" width="280" height="280" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/kindafunny-kinda-funny-greg-miller-the-rules-BCDXLMoKKjyeDXNyLg"></p>
Here are a few rules to remember while creating identifiers:

1. Identifiers can be a combination of letters in lowercase (a to z), uppercase (A to Z), digits (0 to 9) or underscores (_). Names like: `myClass`, `var_1` and `print_this_to_screen`, all are valid examples.

2. An identifier cannot start with a digit. `1variable` is invalid, but `variable1` is a valid name

3. Keywords (in the chart above) **cannot** be used as identifiers

4. We also cannot use special symbols like !, @, #, $, % etc. in our identifiers!

**Look what happens if you use a keyword as an identifier for a variable** ⬇️ <br>

```python
global = 1
```
**Output:**
```python
File "<interactive input>", line 1
    global = 1
           ^
SyntaxError: invalid syntax
```
<iframe src="https://giphy.com/embed/LOVMoi1qYWJyw" width="380" height="219" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/nooooo-LOVMoi1qYWJyw"></p>

**Look what happens if use special symbols like !, @, #, $, % etc. in our identifiers!**  ⬇️ 
```python
a@ = 0
```

**Output:**
```python
  File "<interactive input>", line 1
    a@ = 0
     ^
SyntaxError: invalid syntax
```

*Tips to remember:*
- Python is a case-sensitive language! So `variable` and `Variable` aren't the same😎 
- Always give identifiers a name that makes sense for what you're creating. While `b = 10` is a valid name, writing `books = 10` would make more sense, and it would be easier to figure out what it represents when you're looking back at your code (or having others read it!).
- Multiple words can be separated using an underscore, like `this_is_an_acceptable_identifier`

_______
### <a id="statements">Statements</a>

Instructions that a Python interpreter can execute are called **statements.** For example, `a = 1` is an *assignment statement.* 

### Multi-line statements
In Python, the end of a statement is usually marked by a newline character (\n) like, `print("This is using the newline char\n")`. But, we can make a statement extend over multiple lines with the line continuation character (\). Here's an example ⬇️ 
```python
a = 1 + 2 + 3 + \
    4 + 5 + 6 + \
    7 + 8 + 9
```
In Python, a line continuation is implied inside parentheses (), brackets [], and braces {}. For instance, we can implement the above multi-line statement like so ⬇️ 
```python
a = (1 + 2 + 3 +
    4 + 5 + 6 +
    7 + 8 + 9)
```

Here's an example with brackets [] ⬇️ 
```python
colors = ['blue',
          'purple',
          'orange']
```

You can *also* put multiple statements in one line using **semicolons** ⬇️ 

```python
a = 2; b = 4; c = 6
```
____
### <a id="commentz">Comments</a>

Comments are super easy! And very important. Use them to describe exactly what you're doing for anyone who has to look at your source code, as well as for your own personal use. 

Here's an example of comments in Python:
```python
#I am 
#a comment
print("comments rock")
```
You can *also* create multi-line statements! You can use hashtags `#` or **a set of 3 single or double quotes:** ` ' ' '` or  `"""` 
Look below ⬇️ 
```python
#An example of
#Multi-line
#comments 
```
An example with quotes:
```python
"""This is also a
perfect example of
multi-line comment"""
```
______

### <a id="indention">Indention </a>

Indention is** SO IMPORTANT** in Python! 

Most programming languages like C, C++, and Java use braces { } to define a block of code. Python uses **INDENTATION** 😎  

Here's the breakdown: a code block (the body of a function, loop, etc.) starts with indentation and ends with the first unindented line. The amount of indentation is up to you, but it *has to be consistent* throughout that entire block. 

Usually, four whitespaces are used for indentation and are preferred over tabs. Let's look at some examples ⬇️ 

```python
for i in range(1,100):
    print(i)
    if i == 10:
        break
```
See how nice and clean the above code looks? You can thank white space for that 😉 

Indention *can* be ignored in single line continuations, like below ⬇️ 

```python
if True: print('Howdy partner'); a = 5
``` 
But, doesn't it look a bit unorganized compared to this indented version? ⬇️ 

```python
if True:
    print('Howdy partner')
    a = 5
```

<iframe src="https://giphy.com/embed/ui1hpJSyBDWlG" width="380" height="221" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/ui1hpJSyBDWlG"></p>

____________

You made it to the end! Thanks for reading! 😃
<iframe src="https://giphy.com/embed/lD76yTC5zxZPG" width="380" height="252" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/the-end-thats-all-folks-lD76yTC5zxZPG"></p> 
### In Part 2, I'll be going over:
- **Variables** (Python variables, constants, literals and their use cases)
- **Collections** (to hold variables, literals, constants, etc. --> Dictionaries, lists, tuples, sets) 

I'll be uploading parts of this series *weekly!* **Part 2 coming 8/21/2021!** See you then 😉 