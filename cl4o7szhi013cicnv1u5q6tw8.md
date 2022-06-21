## How to Import Data in Oracle SQL Developer Web


Howdy coders! This blog post is going to cover **how you can create a new table in Oracle SQL Developer Web using imported data from .CSV file** 💪🏽 

If you haven't set up your *'Always Free' *Oracle Cloud account (it's literally *always free *LOL) and created a Database yet, [click here and follow the steps in this blog post before following this one.](https://laylacodes.hashnode.dev/creating-an-atp-database-with-oracle-sql-developer-web)

Let's get jiggy with it 😎

______
### Steps
______
#### Step 1) Sign In

Go to oracle.cloud.com and sign in! (Save your log-in info for quick access)
_____
#### Step 2) Choose your Database

Click on `Autonomous Database` listed under Service Links. 

![ss1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655382080501/E-gGoknVV.png align="left")

📌 **And if you can't find `Autonomous Database` in Service Links, type the name of your Database in the search-bar. ** Like I did below:

![ss3.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655385314654/EttuqaEaL.png align="left")
My Database name is 'beautifulsoop', so if I just type that in the search-bar, press Enter... my database will show up! 

So, now click the name of your Database & that'll take you directly to your `Autonomous Database Details` page that looks like this:

![ss4.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655385530521/Qhe02YHLM.png align="left")
___
#### Step 3) Click on `Database Actions`
_____
#### Step 4) Click on `SQL`


![ss5.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1655473257705/-mbsoRuWz.jpg align="left")
📌 (Fun fact: you can bookmark this page to be able to refer back to your Database Launchpad **directly!**)
______
#### Step 5) Click the `...` 
![ss9.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655474103129/TwkZXx4cO.png align="left")

And click `Data Loading` ► `Upload Data Into New Table`

![ss8 (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655474159584/lCTNr5RU7.png align="left")

Then, *upload your file!* Notice how it automatically grabs column names to be created? 
![ss10.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1655491916916/16TPvVh-Q.jpg align="left")

Click `Next` to define your data types, a Primary Key, what can be Null, etc. 
Shown here: 
![ss11 (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655494647644/_P4TdHdAL.png align="left")

Click `Next` to review the details of your new table. Notice how it shows the *actual* DDL code that would be used to create the table and insert the data! It also shows you what cells from your spreadsheet file have been turned into column names.

See below:
![Generated DDL Code.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655500761369/TIl-vwNjL.png align="left")

Follow the GIF below to see the whole process:

<iframe src='https://gfycat.com/ifr/ShadyAstonishingIndusriverdolphin' frameborder='0' scrolling='no' allowfullscreen width='600' height='355'></iframe>

Now, your table is created, and populated with all the data from the file you uploaded! **SO EASY, RIGHT?** 💪🏽 and now when you run the query `SELECT * FROM your_new_table_name_here;` --> the table you just created with all your file data will show up! 

See below:


![new table.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655501495212/KlDVVOWTU.png align="left")

______

AND FIN - you just learned how to upload data into your database using Oracle SQL Developer Web! 😎  literally only takes 5 steps!

<iframe src="https://giphy.com/embed/S9i8jJxTvAKVHVMvvW" width="300" height="170" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/parksandrec-parks-and-recreation-rec-peacocktv-S9i8jJxTvAKVHVMvvW"></a></p>

If you have any questions, don't hesitate to drop them in the comments below OR ping me on Twitter --> [@pilatesdev](https://twitter.com/pilatesdev)

🧡 see you in my next post


