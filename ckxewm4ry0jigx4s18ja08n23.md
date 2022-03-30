## How to Make a Bash Script Executable in Linux

Hey coders! 🧡

I completed my Linux Operating System course this semester *(with an A!!!!)* 🥳, and wanted to blog about a few fun things I've learned in the class! 

<iframe src="https://giphy.com/embed/HCkbgKLdLWq3OCV8YM" width="280" height="230" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p></p>

Let's talk about how you can make a Bash script executable 🤠

_______

<h3>Step 1: Create a new text file</h3>

First, we have to create a file to write our script in. I use the Vim editor mainly, so I'll be demonstrating the example within Vim! 

To create a new file in Vim, type: `vi MyNewScript.sh` in the command line, like below


![Screen Shot 2021-12-05 at 2.03.56 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638734643971/nLDbXAs8i.png)

____
<h3>Step 2: Add #!/bin/bash </h3>

Don't forget to add your *sha-bang* to the top of your Vim (or Nano) file! This is key for 'making it executable'.

![Screen Shot 2021-12-05 at 2.10.53 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638735058744/pyq0PZEqX.png)

_________

<h3>Step 3: Add your script! </h3>

This is where the fun begins 🤠 you can easily automate simple processes in a function *within* your Bash script! Here's an example ⤵️


![Screen Shot 2021-12-05 at 2.45.26 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638737132809/yxVa0NVwr.png)

In the above script example, I created a function, `CreateDir()`. When called, `CreateDir` should accept a new directory name as a command-line argument and then create a new directory (if you don't already have a directory created with the same name!) 

___________

<h3>Step 4: At the command line, run chmod u+x </h3>

![Screen Shot 2021-12-05 at 2.27.36 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638736061852/uraidgI74.png)

Wondering what `chmod u+x` does? 
It grants only the owner of that file execution permissions. (Basically making it only executable for the owner of the file.)
__________

<h3>Step 5: Run your script! </h3>

To run your new script, simply type `./YourScriptFileName.sh`! (The key is using `./` in front of your script file.)

![Screen Shot 2021-12-05 at 2.41.36 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638736900243/IoLgLcv4H.png)

As you can see above, the script successfully catches a duplicate directory name, and won't allow it to be created. 🤠 yeehaw!

________

<iframe src="https://giphy.com/embed/cXblnKXr2BQOaYnTni" width="300" height="250" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/theoffice-the-office-tv-moroccan-christmas-cXblnKXr2BQOaYnTni"></a></p>

and voila!! That is the simple process of making a script executable in Linux 🥰

Stay tuned for more articles on Vim in Linux, cronjobs, etc.! I have some fun Linux content planned 🧡

If this helped you, give me follow on Twitter [here](https://twitter.com/codinglay)! I hope you have an amazing rest of your day!!










