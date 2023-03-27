---
title: "The Difference Between Span and Div"
datePublished: Mon Sep 27 2021 13:27:30 GMT+0000 (Coordinated Universal Time)
cuid: cku2oqx2403ykk6s1aa8vd889
slug: the-difference-between-span-and-div
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632601163599/9IP8A-FUV.png
tags: programming-blogs, web-development, webdev, html5, frontend-development

---

What's up, coders!!

Let's be honest: do you *TRULY* know the difference between the HTML tags `<span>` and `<div>`?? 🤔

Most people just use tons of `<div>`'s and call it a day -- BUT, the almighty `<span>` tag is just as useful! Let's take a look ⬇️

### Table of Contents

* #### [`Summary 😎`](#tldr)
    
* #### [`What does <span> do?? 😍`](#span)
    
* #### [`What does <div> do?? 🥸`](#div)
    
* #### [`Codepen Examples 🕺`](#example)
    

---

### `Summary 😎`

**BOTH** `<div>` and `<span>` group together related parts of a webpage, but they *both* serve different functions 👀

They're mainly used to group together chunks of HTML, and hook information onto that chunk of HTML! **Most commonly**,`<span>` and `<div>` are used with the CSS attributes `class` and `id` to associate the element with a certain CSS class or id selector. 🥰

🌟 Note that `<span`\&gt; and `<div>` **are not Semantic!** Get a review on your [Semantic HTML tags here!](https://laylacodes.hashnode.dev/semantic-html-tags-a-break-down) 🥳

Here's an example of `<div>` and `<span>` being used together ⬇️

```plaintext
<div id="cat">
    <p>I love my cat <span class="meow">SO MUCH</span></p>
</div>
```

Within the `<div>`, the `<span class="meow">` gives the words *'SO MUCH'* whatever style you create in the CSS file with the `.meow` selector!

Let's break down `<div>` and `<span>` individually ⬇️

<iframe src="https://giphy.com/embed/dMsh6gRYJDymXSIatd" width="310" height="209" class="giphy-embed"></iframe>

---

### `What is <span> ?? 🤯`

The `<span>` element is an **inline element**, typically used to apply styling to a portion of inline content!

**What's an inline element?**

An inline element *does not start a new line* and only takes up as much space on the page as its content.

`<span>` tags are used on small portions of text, links, images, and other HTML elements that appear in line with the content around it.

**Summary:** `<span>` is usually used to apply styling to a portion of inline content!!

Check out an example ⬇️

```plaintext
<span id="span-0"> This text is inside a span element. </span>
<span id="span-1"> This text is inside another span element. </span>
```

---

### `What is <div> ?? 🥸`

The `<div>` element is a generic block-line element, most often used to divide page content into blocks!

**What's a block-line element?**

A block-line element starts a *new line before and after* the content encased in the tag and has a width equal to the entire page *or* the parent container 😎

You’ll often see divs used to group related paragraphs, images, headings, and links together!! **(But,** `<div>` should NOT be abused too much! Don't forget your Semantic HTML! Click [here](https://laylacodes.hashnode.dev/what-is-semantic-html) for a reminder) 👀

A basic example of `<div>`'s look like this ⬇️

```plaintext
<div id="div-0">
  <h2>This is a heading inside a div element</h2>
  <p>This a paragraph inside  a div element.<p>
</div>

<div id="div-1">
  <h2>This is a heading inside a div element</h2>
  <p>This a paragraph inside  a div element.<p>
</div>
```

---

### `Examples 🤯`

Let's look at the above blocks of code in Codepen to solidify your understanding ⬇️

%[https://codepen.io/codinglayla/pen/MWoroaO] 

And here's the second example ⬇️

%[https://codepen.io/codinglayla/pen/XWgVgXq] 

---

### and that's all, folks! 🥳🥳

Thank you for reading this far!! I hope this helped clear up any confusion you had about `<span>` and `<div>` 🧡 feel free to drop me any questions or shoot me a DM on Twitter if you're still confused!

<iframe src="https://giphy.com/embed/cdNSp4L5vCU7aQrYnV" width="240" height="380" class="giphy-embed"></iframe>

Give me a follow here on [Hasnode](https://hashnode.com/@laylacodes) or [Twitter](https://twitter.com/pilatesdev) if you enjoyed this post 🥰🥰