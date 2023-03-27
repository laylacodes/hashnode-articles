---
title: "Semantic HTML Tags: a Break Down"
datePublished: Tue Sep 07 2021 16:56:21 GMT+0000 (Coordinated Universal Time)
cuid: cktabegnr04f87ts12umh4vre
slug: semantic-html-tags-a-break-down
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1630806176926/AvTzCHO7Y.png
tags: web-development, html, html5, frontend-development

---

Howdy, folks! Thanks for checking out my article 😊 if you're not too familiar with Semantic HTML, check out my article on the topic [here!!](https://laylacodes.hashnode.dev/what-is-semantic-html) Otherwise, let's get jiggy with it 🥳🥳🥳

<iframe src="https://giphy.com/embed/cdNSp4L5vCU7aQrYnV" width="240" height="380" class="giphy-embed"></iframe>

### Table of Contents 💃

* #### [`A List of Semantic HTML Tags`](#list)
    
* #### [`<article> and <section>`](#article)
    
* #### [`<header> and <hgroup>`](#header)
    
* #### [`<aside>`](#aside)
    
* #### [`<figure> and <figcaption>`](#fig)
    
* #### [`<footer>`](#footer)
    

---

### A List of Semantic HTML Tags

I created this handy dandy list of Semantic HTML tags for HTML noobs (like myself) 😎😎 Check it out ⬇️

![cheathseet.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1630797860991/s1derlYId.jpeg align="left")

💕 The tags we're going to be dissecting in this article are:

1. `<article>` and how it differs from `<section>`
    
2. `<header>` and how it differs from `<hgroup>`
    
3. `<aside>`
    
4. `<figure>` and how it differs from `<figcaption>`
    
5. `<footer>`
    

---

### `<article> and <section>` 🤯

Here's the breakdown 😎

**Both of these tags are meant for sectioning content**. `<section>` is basically `<article>`'s workmate, so they can be used interchangeably - it just depends on the situation!

`What is <article>?` 🤨

It's a container for forum posts, a magazine or newspaper article, blog entry, product card, a user-submitted comment, an interactive widget/gadget, or any other independent piece of content!

*Further explanation:* When each item of content can be read on their own, and it would make sense organized as separate items in an RSS feed, then `<article>` is the suitable tag.

`What is <section>?` 🤔

This element represents a standalone section of a document, which doesn't have a more specific semantic element to represent it. `<section>`'s should always have a heading!

**To decide which one of these semantic tags you should use, here are a few questions to ask yourself:** 🤩

1. Does the content have a different author than the page?
    
2. Could the content be a separate entry in a feed?
    
3. Could the content still make sense if it was printed out w/o any other content or context?
    

If you answered 'yes' to 1-2 of the questions above, using `<article>` is best! Otherwise, use `<section>`.

💫 **Fun fact:** You can actually nest multiple `<section>`'s inside `<article>` or even vice versa! Take a look at this cheat sheet I've created to visualize this ⬇️

![articlelayout.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630799283615/k52H1LDN0.png align="left")

You can nest multiple`<article>`'s inside of a `<section>`, let's see how ⬇️

```plaintext
<section>
  <p>Most Popular Stories</p>
  <section>
    <p>News</p>
    <article>News Story 1</article>
    <article>News Story 2</article>
    <article>News Story 3</article>
  </section>
  <section>
    <p>Sports</p>
    <article>Sports Story 1</article>
    <article>Sports Story 2</article>
    <article>Sports Story 3</article>
  </section>
</section>
```

---

### `<header> and <hgroup>` 😊

`What is <header>?` 🤔

The `<header>` element is generally found at the top of a document, a section, or an article! It usually contains the main heading along with some navigation and search tools specific to your webpage.

Take a look at the example block of code below ⬇️

```plaintext
<header>
  <h1>Portfolio Page</h1>
  <ul>
    <li><a href="/home">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact me here</a></li>
  </ul>
  <form target="/search">
    <input name="q" type="search" />
    <input type="submit" />
  </form>
</header>
```

See how organized it is?

<iframe src="https://giphy.com/embed/KMVcsX5EjDGDK" width="280" height="190" class="giphy-embed"></iframe>

`What is <hgroup>?` 🧐

It's similar to `<header>`! This `<hgroup>` element should be used where you'd like a main heading with one or more subheadings! Take a look at the example ⬇️

```html
<hgroup>
  <h1>Meow Heading 1</h1>
  <h2>Subheading 1</h2>
  <h2>Subheading 2</h2>
</hgroup>
```

💫 **IMPORTANT TO REMEMBER:** the `<header>` element can encapsulate any kind content, but the `<hgroup>` element can only contain other headers, that is `<h1>` to `<h6>` and including `<hgroup>`.

---

### `<aside>` 😃

`What is <aside>?`

This element is meant for content that isn't part of the main flow of text in which it appears, however still related in some way. *Basically*, `<aside>` is a sidebar to your main content 😊

Check out this cheat sheet I created to visualize where `<aside>` could be on your webpage ⬇️

![html semantics.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630800501328/Bt1ovQ-wQ.png align="left")

Here's an example code block of how you'd set up an `<aside>` element:

```html
<aside>
  <p>This is a sidebar. For example, it could contain a 
definition of a term from your main body of content.</p>
</aside>
```

---

### `<figure> and <figcaption>` 😊

`What is <figure> and <figcaption>?` 🤨

The element`<figure>` is meant for wrapping your image content around it, and `<figcaption>` is to caption your image.

Here's a cheatsheet I created to visualize this for you! Check it out ⬇️

![figcaption.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630801861774/mCsD-oEI-.png align="left")

And here's an example block of code ⬇️

```plaintext
<figure>
  <img src="https://i.imgur.com/cU6JIoc.jpg" 
alt="Michiko Malandro anime picture"/>
  <figcaption>Michiko Malandro is an anime character from Michiko and Hatchin.</figcaption>
</figure>
```

---

### `<footer>`

*Where there is a* `<header>`, *there must be a* `<footer>`! 😜😜 A `<footer>` is usually found at the bottom of a webpage/document, a section, or an article.

Just like `<header>`, the content usually contains metainformation, such as author details, legal information, and/or links to related information. 💫 Fun fact: you can include `<section>` elements within a footer!

<iframe src="https://giphy.com/embed/cXblnKXr2BQOaYnTni" width="260" height="200" class="giphy-embed"></iframe>

Here's an example of how you'd set up your `<footer>`:

```plaintext
<footer>
  <p>Author: Seymour Butts</p>
  <p><a href="mailto:seymourbutts@example.com">seymourbutts@example.com</a></p>
</footer>
```

---

## And... you're done!

You made it out alive after reading this long ass post! 🥳🥳🥳

<iframe src="https://giphy.com/embed/ynRrAHj5SWAu8RA002" width="200" height="190" class="giphy-embed"></iframe>

Thank you for reading this long-ass article, I'm sooo grateful! 🥰🥰

I'll be creating more Hashnode blog posts about frontend development as I go through my self-taught frontend journey -- if you enjoyed this post, follow me here on [Hashnode](https://hashnode.com/@laylacodes) and on [Twitter!](https://twitter.com/pilatesdev) 💜

DM me on Twitter or leave a comment if you get confused about any of these! 😜 also, **feel free to download any cheatsheets in this article to use!** 😄