# JavaScript event handlers & event listeners 101

While taking my Web Design course this semester, I finally learned the slight difference between JavaScript event handlers and listeners... so, I'm here to share my newfound wisdom!!

**But, wtf is an** `event`**??**

An `event` is usually triggered by user actions, like clicking a button or entering text into a form field! Or they can be triggered by other actions, like the page finishing loading or an error occurring.

It's **KEY** for frontend developers to show a response to events, for example, a pop-up dialog box confirming a button has been clicked aka, confirmation of submission alert.

There are two ways to handle JavaScript events:

* *Event handlers*
    
* *Event listeners*
    

Both are methods of executing *some code* when an event happens...but which is better?

Let's dive in!!!

<iframe src="https://giphy.com/embed/MZocLC5dJprPTcrm65" width="200" height="200" class="giphy-embed"></iframe>

---

# **Event Handlers**

An `event handler` is a function that's directly assigned to an event property of an HTML element. When the corresponding event occurs, the function (the event handler) is executed!

To use an *event handler*, use one of the `event handler` properties of an object, `onclick`, `onload`, or `onsubmit`. (See a list of all the event properties [here](https://www.elated.com/events-and-event-handlers/)).

*Note: an object can only have* ***one*** *event handler for each event type.*

Here's an example using the event property `onclick`:

```javascript
const button = document.querySelector(".btn")

button.onclick = () => {
  console.log("Button clicked.");
};
```

The `onclick` *event handler* is triggered when the user clicks on the button. And as a response to the event, `"Button clicked."` is output to the console!

---

# **Event Listeners**

The second option to handle JavaScript events is: `event listeners`. An *event listener* is a function that's attached to an HTML element using the `addEventListener()` method. This option works by the event listener *listening* for events and getting triggered when an event happens!

Event listeners allow **multiple functions** to be registered to the **same event**, and also provide the ability to easily *remove* the listener when it's no longer needed.

<iframe src="https://giphy.com/embed/ySkwqIhKRzYO7HX0ie" width="200" height="200" class="giphy-embed"></iframe>

Let’s rewrite the previous code snippet by adding an `event listener` to a button to listen for clicks:

```javascript
const button = document.querySelector(".btn");

// Define named function buttonClick()
function buttonClick() {
  console.log("Button clicked.");
}

// Add event listener using buttonClick()
button.addEventListener("click", buttonClick);
```

I defined a named function called `buttonClick` that logs *"Button clicked."* to the console when executed. Then, an event listener is added to the button element using `addEventListener`, passing in the event type (`"click"`) and the `buttonClick` function!

**You can also *remove*** `event listeners` **by using the** `removeEventListener()` **method!**

Here's an example using the same named function `buttonClick`:

```javascript
// Remove event listener
button.removeEventListener("click", buttonClick);
```

In the code snippet above, I used the `removeEventListener` method on the button element, passing in the same event type (`"click"`) and the `buttonClick` function. That removes the event listener from the button element, so that the `buttonClick` function no longer executes when the button is clicked! 😄

---

# **Event Listeners vs Event Handlers**

Soooo, what's the difference between the two?

> An object can only have one '*event handler*' for a specific event, but it can have multiple '*event listeners'* for the event.

### Let's break it down:

If you add two `event handlers` for the same button click, the second event handler will overwrite the first, and only that second event will output. For example:

```javascript
// Adding two event handlers using anonymous functions
document.querySelector(".btn").onclick = function() {
  console.log("Hello ");
};
document.querySelector(".btn").onclick = function() {
  console.log("World!");
};
// This outputs "World!" out to the console.
```

It's acceptable to have *multiple* `event listeners` of the same event per object. So, let's rewrite the previous code snippet, but using `addEventListener` instead, so both of the triggers will output:

```javascript
// Define two named functions
function sayHello() {
  console.log('Hello ');
}
function sayWorld() {
  console.log('World!');
}
// Get button element and add event listeners
const button = document.querySelector('.btn');
button.addEventListener('click', sayHello);
button.addEventListener('click', sayWorld);
// This outputs "Hello" and "World!" out to the console.
```

*Note: using named functions vs. anonymous functions makes your code more readable and easier to understand, especially if you're creating intricate event listeners!*

---

# **Which one should I use?**

It's usually better to use `event listeners` over `event handlers`!

**Why?**

`Event listeners` offer more flexibility & control in handling events, especially when you're dealing with more complex applications. `Event listeners` can be attached to multiple functions of the same event, which helps keep code organized 🙂

So, in conclusion:  
**Event listeners &gt; event handlers**

---

I hope this helped clear up any confusion you had about event handlers & listeners!! If it did, give me a follow on [Twitter](https://twitter.com/pilatesdev) or here on [Hashnode](https://hashnode.com/@laylacodes) 😄

🧡 My website: [https://laylacodes.github.io/](https://laylacodes.github.io/)