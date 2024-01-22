---
title: "Oracle SQL Developer VsCode Extension Set-Up Guide"
datePublished: Mon Jan 22 2024 20:23:42 GMT+0000 (Coordinated Universal Time)
cuid: clrpdknp1000009k1h2od6pel
slug: oracle-sql-developer-vscode-extension-set-up-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705691549215/30f5ecf7-2364-4a2a-9c63-caaa356118bc.png
tags: databases, developer, sql, vscode-extensions

---

Hi friends!

BIG NEWS! My team at Oracle, Database Tools, has released a **new VsCode extension for Oracle Database**, the new SQL Developer extension! This extension brings the ***full functionality*** of Oracle SQL Developer into your VsCode environment!

*What does this extension do, you ask?* Let me show ya! 😊

[![Click image to view extension in VsCode marketplace](https://cdn.hashnode.com/res/hashnode/image/upload/v1705600734528/d046fb6f-e613-4466-ad52-8172f1326edd.jpeg align="center")](https://marketplace.visualstudio.com/items?itemName=Oracle.sql-developer)

In this article, I'll walk you through:

1. installing the Oracle SQL Developer extension for VsCode
    
2. connecting your Oracle Cloud database to VsCode with an *instance wallet*
    
3. writing your 1st query with the extension
    

**🚨 *Before proceeding with this tutorial, please watch this tutorial below to set up an Oracle Cloud database:***

%[https://www.youtube.com/watch?v=bmCHIJqegJo&t=24s] 

(Or if you're not into watching videos, read its corresponding blog post: [Creating a Cloud Database with Oracle SQL Developer Web](https://www.lay.codes/blog/creating-an-atp-database-with-oracle-sql-developer-web)*)*

---

## Install extension in VsCode

Let's get the new Oracle SQL Developer extension installed in your VsCode environment! Click this link [here](https://marketplace.visualstudio.com/items?itemName=Oracle.sql-developer) to visit the extension in the VsCode marketplace *or* follow the steps below:

![https://cdn.hashnode.com/res/hashnode/image/upload/v1705677242091/1adefdb0-43d9-497b-93cb-3138a631a5a5.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677242091/1adefdb0-43d9-497b-93cb-3138a631a5a5.gif align="left")

Steps:

* click `Extensions` button in VsCode
    
* search `Oracle SQL Developer Extension` in the Extensions search bar
    
* click the extension with this image:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705954490855/e15c5752-6961-4a3e-8d1a-026f83981bd4.png align="left")
    

* click `Install`
    

And, done! The extension is installed - now let's move on to connecting our database to it.

---

## Download Instance wallet

Assuming you've already created an Oracle Cloud database...if not, follow that YouTube video I linked in the beginning of this article ([here's the link again if you missed it](https://www.youtube.com/watch?v=bmCHIJqegJo&t=24s)). We're going to be connecting that cloud database to our VsCode extension! 🔥

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">NOTE: you can also connect on-premise databases, just choose a different Connection Type when setting up your new database connection. <em>Connection Types available in the extension: Basic, Custom JDBC, Cloud Wallet, TNS</em></div>
</div>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705689101647/6199da7b-47bd-4bc5-bdc2-b167822916a8.png align="center")

Let's continue our ***Oracle Cloud database connection setup***...  
Follow the steps below to download your instance wallet for your Cloud database:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677760475/ac29f1d8-2684-43e5-a672-b2c6507d8a5b.gif align="center")

* visit cloud.oracle.com home page (log in, of course)
    
* click `Autonomous Databases` (*or search it in the search bar if you can't find it, see below*)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705614717960/173d6b96-eeb4-4e06-80ef-1a92a72fcfec.png align="center")

* click the database you'd like to connect, mine is called `test`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705611778405/7196ccf4-e88b-47a0-a1fb-0c650bc4a842.png align="center")

* click the `Database Connection` button
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705614785721/9f3f29a7-d717-44c3-bfe0-2cfbf766d999.png align="center")

* choose `Instance wallet`, and then click `Download wallet` -&gt; it'll prompt you to input the 12 character password you used when creating your database
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705614883283/3aa64ede-ca6c-4238-b070-694eef7a1faf.png align="left")

* a `wallet.zip` folder will be downloaded to your computer, ***do not unzip this!***
    

---

## Create DB connection in the Extension

Now that you've downloaded your instance wallet, let's hop back over to VsCode!

Navigate to the SQL Developer extension via the database icon in the Activity Bar and create your database connection, like so:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678337101/5de4a96e-2885-4680-b4f1-206683f9e1a6.gif align="center")

Steps:

* click the `SQL Developer extension` icon, shown below
    
* then, click the `+` icon, that is the button to create a new database connection
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705610405960/b84e9124-87ef-4023-ba29-45b5148426f6.png align="center")

* fill out the details to create a new database connection!
    
    * *Connection name* can be whatever you'd like, username should be `ADMIN` & the password will be the `12 character password` you chose whilst setting up your database :)
        
* in the drop-down menu for *Connection Type*, choose `Cloud Wallet`! Then, in *Details* right below, upload the `wallet.zip` file we downloaded earlier:
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705610791784/ac95f61a-1cdd-4b0c-93b3-87cb18450ebd.png align="center")

---

## SQL query time!

Now to the fun stuff- we can **finally** write and execute SQL & PL/SQL queries! 😎

To create my first table using the Oracle extension, I'll be using the SQL code below. Feel free to copy and paste it to get an idea of how the extension executes code!

```sql
CREATE TABLE employees
    ( employee_id    NUMBER(6),
      first_name     VARCHAR2(20),
      last_name      VARCHAR2(25),
      email          VARCHAR2(25),
      hire_date      DATE,
      salary         NUMBER(8,2),
      manager_id     NUMBER(6),
      department_name VARCHAR2(25)
    );

CREATE UNIQUE INDEX emp_emp_id_pk
ON employees (employee_id);

ALTER TABLE employees
ADD ( CONSTRAINT     emp_emp_id_pk
                     PRIMARY KEY (employee_id),
      CONSTRAINT     emp_manager_fk
                     FOREIGN KEY (manager_id)
                      REFERENCES employees
    );

INSERT INTO employees VALUES ( 100, 'Steven', 'King', 'SKING@company.com', TO_DATE('17-06-1997', 'dd-MM-yyyy'), 24000, NULL, NULL );
INSERT INTO employees VALUES ( 101, 'Neena', 'Kochhar', 'NKOCHHAR@company.com', TO_DATE('21-09-2015', 'dd-MM-yyyy'), 17000, 100, 'Administration' );
INSERT INTO employees VALUES ( 102, 'Lex', 'De Haan', 'LDEHAAN@company.com', TO_DATE('13-01-2011', 'dd-MM-yyyy'), 17000, 101, 'Administration' );
INSERT INTO employees VALUES ( 103, 'Alexander', 'Hunold', 'AHUNOLD@company.com', TO_DATE('03-01-2006', 'dd-MM-yyyy'), 9000, 100, 'IT' );
INSERT INTO employees VALUES ( 104, 'Bruce', 'Ernst', 'BERNST@company.com', TO_DATE('21-05-2017', 'dd-MM-yyyy'), 6000, 103, 'IT' );
INSERT INTO employees VALUES ( 105, 'David', 'Austin', 'DAUSTIN@company.com', TO_DATE('25-06-2015', 'dd-MM-yyyy'), 4800, 103, 'IT' );
INSERT INTO employees VALUES ( 106, 'Valli', 'Pataballa', 'VPATABAL@company.com', TO_DATE('05-02-2006', 'dd-MM-yyyy'), 4800, 103, 'IT' );
INSERT INTO employees VALUES ( 107, 'Diana', 'Lorentz', 'DLORENTZ@company.com', TO_DATE('07-02-2017', 'dd-MM-yyyy'), 4200, 105, 'IT' );
INSERT INTO employees VALUES ( 108, 'Nancy', 'Greenberg', 'NGREENBE@company.com', TO_DATE('17-08-2002', 'dd-MM-yyyy'), 12008, 100, 'Finance' );
INSERT INTO employees VALUES ( 109, 'Daniel', 'Faviet', 'DFAVIET@company.com', TO_DATE('16-08-2002', 'dd-MM-yyyy'), 9000, 108, 'Finance' );
INSERT INTO employees VALUES ( 110, 'John', 'Chen', 'JCHEN@company.com', TO_DATE('28-09-2005', 'dd-MM-yyyy'), 8200, 108, 'Finance' );
INSERT INTO employees VALUES ( 111, 'Ismael', 'Sciarra', 'ISCIARRA@company.com', TO_DATE('30-09-2015', 'dd-MM-yyyy'), 7700, 110, 'Finance' );
INSERT INTO employees VALUES ( 112, 'Jose Manuel', 'Urman', 'JMURMAN@company.com', TO_DATE('07-03-2006', 'dd-MM-yyyy'), 7800, 110, 'Finance' );
INSERT INTO employees VALUES ( 113, 'Luis', 'Popp', 'LPOPP@company.com', TO_DATE('07-12-2007', 'dd-MM-yyyy'), 6900, 110, 'Finance' );
INSERT INTO employees VALUES ( 114, 'Den', 'Raphaely', 'DRAPHEAL@company.com', TO_DATE('07-12-2002', 'dd-MM-yyyy'), 11000, 100, 'HR' );
```

I've created a folder *Intro to PL/SQL Exercises* for practice, and I have a few files of SQL already populated within the folder:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679967458/e479fccf-d0cd-4cd6-9e5d-2a9328a18ea7.gif align="center")

To try it out for yourself: Create a file `employee.sql` and copy/paste that code above into your editor

* Save it, then press `F5` **or** click the `Run Statement` button, to execute the SQL script shown below:
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705614199298/85972e3b-6c2a-44b6-b530-9564353ec023.png align="center")

* Once the statements are finished executing, your table is now created! Write in a `SELECT * FROM employees` query in the `employees.sql` file, then highlight that line, and press the `Run Statement` button, shown below:
    

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">the <code>Run Statement</code> button is how you can run individual statements vs. running the entire script/file</div>
</div>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705614290062/627913e8-4b40-45fe-8dbe-a5280102c175.png align="center")

After running the `SELECT` statement, your query result will display like so:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705613958875/cf31a74f-76fb-43e8-830d-a4a58565ddf9.png align="center")

---

Congrats, you've officially connected your Oracle Cloud Database to VsCode, and created your first table! :)

%[https://giphy.com/gifs/season-17-the-simpsons-17x10-xT5LMHxhOfscxPfIfm] 

I'm so excited to see what all everyone does with this new incredible extension! And if you haven't tried it out yet, I hope my enthusiasm has persuaded you to give it a try – I'm confident you'll find it worthwhile! 😊  
  
[**If you DO like the new extension, please give it a 5 star rating on the Visual Studio Marketplace for me! That would mean so much to the Database Tools team (who created this extension) and myself.**](https://marketplace.visualstudio.com/items?itemName=Oracle.sql-developer)

And lastly, you have any questions or concerns, please don't hesitate to ping me on X! 🧡 My personal website, with all my contact info: [lay.codes](https://lay.codes)