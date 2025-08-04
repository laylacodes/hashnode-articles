---
title: "Interactive SQL examples in your blog, using LiveSQL"
datePublished: Mon Jul 28 2025 19:13:00 GMT+0000 (Coordinated Universal Time)
cuid: cmdnhjtax001c02l42ybmg195
slug: interactive-sql-examples-using-livesql
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1753730170534/4f4ef534-b9ef-4167-9884-5e6a95aba7c2.jpeg
tags: blogging, databases, sql, howtos

---

Ever wish your blog’s readers could go from “wow, that’s cool” to “let me try that!” in a heartbeat? That’s exactly what [**Oracle Live SQL**](https://livesql.oracle.com/next/) makes possible. It’s a free, cloud-based SQL playground that lets you write, run, and share Oracle SQL snippets—no local setup needed.

Now, thanks to two new features—the **Run in Live SQL** button and the **Live SQL Embedded Editor**—you can turn those static code blocks in your blog into an interactive, hands-on experience 🤙🏽 No clunky .zip downloads. No manual copy-pasting. Just one tap, and boom: your SQL runs live in Live SQL! 🤗

The Live SQL team has created two options for you to share interactive snippets with your audience:

1. **Run in Live SQL** button: a one-click link that opens your snippet in Live SQL
    
2. **Embedded Editor** iframe: a fully interactive editor *right on your page*
    

Below, I’ll walk you through how to set each up; complete with screenshots and best practices—so your post is both informative and hands-on. Let’s get crackin’!

---

## Why Add Interactive SQL Snippets?

Embedding runnable examples…

* **Engages readers** by letting them experiment with your code right then and there
    
* **Demonstrates concepts** more clearly than static code or screenshots
    
* **Boosts time on page** as readers play with queries, experiment with concepts, etc.
    

---

## “Run in Live SQL” Button

### **Step 1: Copy your shareable URL**

* Paste your SQL snippet into Live SQL and click **Share**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1754064205908/ca177b1f-b99f-4c7c-a2ed-cb0ebc6c1a75.png align="center")
    

* In the dialog, scroll down and select **Run in Live SQL Button**.
    

* Click **Copy Code** at the bottom of the drawer to grab your `compressed_code` URL.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1754066280952/d04b9193-acc7-4ddf-b2d4-563ca7acdf6f.gif align="center")
    

> **Fallback:** If you really need the full HTML snippet, switch to the **Show Code** tab shown in the GIF above and click **Copy**.

### **Step 2: Insert the button in your blog**

* **If your platform supports raw HTML**  
    Simply paste the `<a>` tag you got from the previous step:
    
    ```plaintext
    <a href="https://livesql.oracle.com/next/?compressed_code=…&code_language=PL_SQL"
       style="background-color:black;color:white;padding:0.4rem;border-radius:0.25rem;display:inline-flex;align-items:center;text-decoration:none;"
       target="_blank" rel="noopener">
      <img src="ICON_URL" alt="Run in Live SQL" style="width:20px;height:20px;margin-right:0.4rem;">
      <span>Run in Live SQL</span>
    </a>
    ```
    
* **If your platform only lets you use Markdown**  
    Host the button graphic somewhere public (GitHub, CDN, etc.), then drop this into your post:
    
    ```plaintext
    [![Click here to run in Live SQL](ICON_URL)](LIVE_SQL_SHARE_URL)
    ```
    
    * **ICON\_URL**: link to your hosted button image
        
    * **LIVE\_SQL\_SHARE\_URL**: the `compressed_code` link you copied
        

Either approach renders a clickable button that launches your snippet in Live SQL, like shown below:

[![Run in Live SQL](https://raw.githubusercontent.com/laylacodes/sqlproject/d332d4e93413711255815dcf3772414b3276cf0a/runinlivesqlicon.jpg align="left")](https://livesql.oracle.com/next/?compressed_code=H4sIAAAAAAAAEwt29XF1DuFSUFBQUPdIzcnJV%252FDJLEtVCA70UVRXcAxWcA9ydQ3x9HPncgvy9wUrcwl19LHW1XX1dwYAVcSuejwAAAA%253D&code_language=PL_SQL&code_format=false)

---

## Embedded Live SQL Editor

<iframe id="live-sql-embedded" src="https://livesql.oracle.com/next/embedded/?layout=vertical&amp;compressed_code=H4sIAAAAAAAAEwt29XF1DuFSUFBQUPdIzcnJV%252FDJLEtVCA70UVRXcAxWcA9ydQ3x9HPncgvy9wUrcwl19LHW1XX1dwYAVcSuejwAAAA%253D&amp;code_language=PL_SQL&amp;code_format=true" height="460px" width="100%" style="width:100%;border:1px solid #e0e0e0;border-radius:12px;overflow:hidden">Live SQL Embedded Playground</iframe>

### Step 1: Get the Embed Code

* Back in Live SQL, click the **Share Code** button → **Embedded Editor**
    
* Click the **Show Code** toggle.
    
* Copy the `<iframe>` snippet provided, like shown below
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1754066530739/dcd09ce3-1fc7-4630-8506-e95e396b4755.gif align="center")
    

---

### Step 2: Paste the Iframe into Your Blog Post

* Switch your blog to HTML/source view. Or if you use Hashnode, like me, type `/html` in the blog editor to bring up the Insert HTML option.
    
* Paste the iframe where you want the editor to appear.
    
* Save and preview - your live editor should load, complete with *Run*, *Clear*, and formatting tools.
    
* Note the **Read Only** toggle button shown in your embedded editor:
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1754066825625/4d351c0c-d490-40c8-a158-d9fc5d97725b.png align="center")

By default your embedded editor runs in **Read-Only** mode, which only lets visitors play with Live SQL’s sample schemas. Flip on the **Read-Write** toggle and anyone viewing your post can sign in with their own Live SQL account—so they can create tables, modify your snippet, and run queries against their personal schema for a fully hands-on experience! 🤠

---

### Wrapping Up

And that’s it! 🎉 With just a few clicks, you can transform your static SQL snippets into an interactive playground that:

* **Drives engagement** by letting readers tinker with your queries in real time
    
* **Illustrates concepts** far more clearly than screenshots or pasted code
    
* **Keeps folks on your page** as they explore, experiment, and learn with your queries!
    

#### A Few Pro Tips

* **Preload sample data** in your snippet so readers can immediately see meaningful results
    
* **Limit write-mode embeds** to safe, *read-only* queries unless you explicitly want them to modify their own schema
    
* **Annotate your code** with comments and hints—the more guided the experience, the better :)
    

---

> 🔗 **Share your feedback!** If you try this out in your next blog post, tweet at us [@OracleLiveSQL](https://x.com/OracleLiveSQL) or me [@pilatesdev](https://x.com/pilatesdev). We’d love to see what you build!

Happy blogging—and happy querying! 🚀