## Top 10 String Methods in Python😎

## First Hashnode blog post! 🤩 

I had to make my **first Hashnode post ever** about my favorite language ever: Python! I'll be listing out the top 10 most useful Python String methods, while explaining *how* and *when* they can be used,* with what parameters* and what the output looks like! 

So, strap in folks, let's get this Python party started 😎 
<iframe src="https://giphy.com/embed/o75ajIFH0QnQC3nCeD" width="380" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
________________
 
### 📕 Syntax

Sooooo...what the hell are Python String methods? 

In Python, there are roughly *almost 50 built-in Python String methods* that make creating with Python so much easier 🥳 specifically, Python *strings!* 

Since a Python String is immutable **(meaning unchangeable)**, a string method is what we use to change/alter them! String methods take a string you create and returns a new string while the original string remains unchanged. Cool, huh 😜

Focusing on a strings' immutability: once a string is created in Python, its **value cannot be changed ever again.** To elaborate, the **definition of a string cannot be updated once it's set.**  Below is an example of a string:

```str = "a very good string, I am"``` 

The str variable is defined by a value of a string: `"a very good string, I am"`.. and now I can't change it...

*SIKE* 

There is *one way* to alter strings after they've been created...
<iframe src="https://giphy.com/embed/44b1ABtsG7VTy" width="280" height="186" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/parks-and-recreation-ron-swanson-nick-offerman-44b1ABtsG7VTy">

We need to manipulate strings *all the time* in Python, so String methods are the way! 
<iframe src="https://giphy.com/embed/1hAxQTH0HEWS3L0oRF" width="300" height="100" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/this-is-the-way-1hAxQTH0HEWS3L0oRF">

Let's break down some super helpful methods, shall we? 😋

________

### ✨10 Most Important Methods to Know✨

Since there are a **buttload** of string methods in Python, let's begin with the ones I've used most in my Python learning journey so far! I've realized these are the 10 most valuable methods to know:

<iframe src="https://giphy.com/embed/BpGWitbFZflfSUYuZ9" width="280" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/BpGWitbFZflfSUYuZ9">


1. 
`.format()`

The `format()` method formats the specified value(s) and insert them inside the string's placeholder (the curly brackets). 

The syntax is:`{placeholder}.format(value1, value2)`

Parameter break down: Values 1 and 2 are either a list of values separated by commas, a key=value list, or a combination of both. The values can be any data type.

The code snippet below returns the newly formatted string based on the string value (`"For only ___ dollars"`) and the values passed on the placeholder position ($88 formatted to float to 2 decimal places).

```python
txt = "For only {price:. 2f} dollars!"
print(txt.format(price = 88))```

_____


2.
 `.split()`

This method is used to divide any string data based on any particular separator/delimiter you or the user provides, and inserts that edited data into a list. `split()` can take two arguments and both are optional. 

The syntax is: `string.split(separator, maxsplit)`

Parameters breakdown: Separator specifies the separator to use when splitting the string. By default any whitespace is a separator. Maxsplit defines how many splits to do; the default value if you enter nothing is -1, which is "all occurrences".

```python
 [txt = "If the salad, comes on top, I send it back"
x = txt.split(", ")
print(x)```]

In the code snippet above, the split method is used with the string `txt` with the seperator being `,`. The result printed from using a comma as a separator is as follows:
```python
['If the salad', 'comes on top, 'I send it back']```

___

3.
`join()`	

This method is used to create a new string by combining other strings with a string, list of strings, or tuple of strings data. 

Syntax is as follows: `separator.join(iterable)` (**The separator MUST BE A STRING**)

Parameter break down: Any iterable object where all the returned values are strings. So, dictionaries, lists, tuples.

Below is a code excerpt with a few examples as to how you can use `.join()`:

```python
# Apply join on string data
print('Joining each character with comma:', ','.join('lol))
# Apply join on list of strings
print('Joining list of strings with space:', ' '.join(['I','love', 'programming']))
# Apply join on tuple of strings
print('Joining tuple of strings with colon:', ':'.join(('8675309','Layla', '10','45')))```

Output:
```python
Joining each character with a comma: l,o,l
Joining list of strings with space: I love programming
Joining tuple of strings with colon: 8675309:Layla:10:45```

_____

4.
`strip()`	

This method uses to trim whitespaces from the string object. There are actually *two other related methods *for removing white spaces:

- `lstrip()` method to remove the white space from the left side and 
- `rstrip()` method to remove the white space from the right side of the string. This one for the right side of the string takes no arguments.

The syntax is: `string.strip(parameter)`. 

Parameter breakdown: A set of characters to remove as leading/trailing characters. Below is a code excerpt example:

```python
txt = "     mango     "

x = txt.strip()

print("of all fruits", x, "is my favorite")```

And the output is as follows:

```python
of all fruits mango is my favorite```

_____

5.
`len()`	

This method takes any string value as an argument and returns the total number of characters of that string. It counts spaces, punctuation, and all characters the same. Syntax is as follows: `len(string)`.

Parameter break down: **A string!** Duh 

```python 
# Define a string value
strValue="Python is the best lang ever"

# Print the string value
print("The string value:",strValue)
 
# Apply the len() method
print("Total characters:",len(strValue))```

And the output is as follows:

```python
The string value: Python is the best lang ever
Total characters: 28```

______

6.
`upper()`	

We can convert a string to uppercase in Python using str.upper() function.
lower(). Using this method gives us a new string in all uppercase! This method takes 0 parameters and the syntax is: `string.upper()`

This method is fairly simple, but here's an example to make sure you got it 100%:
```python
txt = "Netflix needs to bring back the office"

x = txt.upper()

print(x)```

Which prints out the following text:

````PYTHON
NETFLIX NEEDS TO BRING BACK THE OFFICE
````


_______

7.
`replace()`	

Python string replace() function is used to create a new string by replacing some parts of another string.

The syntax is: `string.replace(search_string, replace_string [,counter])`

Parameter break down: 
- *search_string* is the string to search for.
- *replace_string* is the string to replace the old value with
- *counter *is an optional parameter,  but it needs a number specifying how many occurrences of the old value you want to replace. The default is all occurrences!

Here's an example:

```python
txt = "one one was rambunctious, two two was like one too"

x = txt.replace("one", "three")

print(x)```

The example excerpt prints out the following:

```python
three three was rambunctious, two two was like three too.```

To elaborate on the example, `"three"` is the replacement value for "`one"`.

______

8.
`capitalize()` 

This method is used to capitalize the first character of the string data and make the remaining characters to lower case! The syntax is as follows: `string.capitalize()`. This method takes 0 parameters!

Example:
```python
txt ="you have won a dundee award!"

x = txt.capitalize()

print (x)```

The example prints out the following:

```python
You have won a dundee award!```

_____

9.
`find()`	

This method is used to search the position of a particular string in the main string and return the position if the string exists in the main string! It finds the first occurrence of the specified value if you only use 1 parameter.

Check out the syntax: `string.find(value, start, end)` 

Parameter break down: 
- *value* is the value you're searching for in the string
- *start* is the value to input to designate where to start the search (optional parameter)
- *end* is the value to input to designate where to end the search; default is the end of the search (optional parameter)

**If the *value* is not found,** the find() method returns -1, but the index() method will raise an exception:

```python
-1
Traceback (most recent call last):
  File "demo_ref_string_find_vs_index.py", line 4 in <module>
    print(txt.index("q"))
ValueError: substring not found```

Here's an example of a successful method using 1 parameter:

```python
txt = "Hello, welcome to Python world."

x = txt.find("e")

print(x)```

Output is as follows:

```python
1```

*Elaborating on the output,* "1" as an output means the first instance it found: 'e', was at placement 1 (since strings/lists/dicts/tuples etc. start at 0)


____

10.
`count()` 


This method is used to count how many times a particular string appears in a text! The syntax is as follows: `string.count(value, start, end)`. 

Parameter breakdown: 
- *value* is the string value to search for
- *start* is optional; it's the position to start the search. If you skip this parameter, it uses a default of 0
- *end* is optional; it's the position to end the search. If you also skip this parameter, it uses the default is the end of the string

Here's an example:

```python
txt = "I love apples, apple are my favorite fruit"

x = txt.count("apple", 10, 24)

print(x)```

Output is as follows:

```python
2```
_____

# HALLELUJAH 

You made it out alive after reading this long ass post! 🥳🥳🥳 Thank you for reading this far, I'm so grateful!
<iframe src="https://giphy.com/embed/czoS1CAP2YZBS" width="280" height="100" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/television-the-office-nbc-czoS1CAP2YZBS">

I'll be creating more Hashnode blog posts about Python in hopes they all mesh together & make your Python creating experience more fluid -- if you enjoyed this post, follow me on Hashnode and [on Twitter!](https://twitter.com/codinglay) 

DM me on Twitter or leave a comment if you get confused about any of these! 

Catch you on the flippity flip! 😆
<iframe src="https://giphy.com/embed/cXblnKXr2BQOaYnTni" width="280" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/theoffice-the-office-tv-moroccan-christmas-cXblnKXr2BQOaYnTni">










