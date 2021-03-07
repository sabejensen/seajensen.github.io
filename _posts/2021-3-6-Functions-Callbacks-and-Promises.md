---
layout: post
title: Functions, Callbacks, & Promises
---

**Functions**

There are a few different ways to declare a function in Javascript. The first and most obvious is to just use the function keyword. 
```
function helloWorld() {
    console.log('Hello world')
}
```
You can also use the function keyword to assign a function to a variable, like so:
```
const greeting = function() {
    console.log('Hello world')
}

greeting()
```
Alternatively, ES6 in Javascript strips this down to something far simpler using arrow functions. They're less intuitive to people who aren't familiar with them, but developers like the extra speed and simplicity they afford your code.
```
const greeting = () => {
    console.log('Hello world')
}
```
If you're only seeking to return something, you don't even have to put it inside brackets. You can just put an entire function on one line.
```
const greeting = () => 'Hello world'
```

**Callbacks**

If you've worked with Javascript for very long, you might have found yourself using callbacks without even knowing what they are. A callback is when you pass a function into another function as an argument. As code gets more complex and asynchronous, callbacks can be useful for performing a series of actions in the right order. 

When you perform a callback, you can make sure you perform some amount of actions first before you call on a function. They can be especially useful when making API calls. When generating a whole page from an API, it's often necessary to break the actions you're performing up into pieces. Callbacks become essential at that point. Working with APIs are when I've used them the most. 

**Promises**

Promises are used heavily in asynchronous Javascript. They allow you to perform an action, then tell the code what to do depending on the result of that action. For example, if you're pulling data from an API, it might take a few moments to make that request. Additionally, you'll want to have a plan of action if the request fails altogether so the user gets some sort of feedback. Promises are great for this purpose. 

Promises can exist in one of three states:

Pending - When it's first initialized and it is neither fulfilled or rejected.
Fulfilled - The operation of the promise was completed successfully.
Rejected - The promised operation failed. 

When the promise goes from "pending" to "fulfilled" or "rejected," the code will move to the next step. Oftentimes, this comes in the form of a .then() method. 
```
const greeting = new Promise((resolve, reject) => {
    setTimeout(() => {
        console.log('A B C')
        resolve('Promise completed')
    }, 3000)
}).then(() => {
    console.log('D E F')
})

// Expected output: 'A B C', 'D E F'
```
Normally in our code, everything would run quickly and synchronously. If we had a setTimeout telling it to wait for three seconds, the rest of the code would probably finish executing first. However, using promises we're able to tell one part of the code not to execute until the promise resolves. In conjunction with callbacks, the tools at our disposal are vastly increased. 

**Async / Await**

Async is a keyword that turns functions into async functions. Async functions will allow us to use the await keyword. Await is a simple and easy way to use the power of promises in Javascript. Simply put, it tells the code not to continue executing until the line with the "await" keyword resolves. 
```
const greeting = async () => {
    const name = await getName()
    console.log('Hello ', name)
}
```
In this example, we can tell the code to await "name" being assigned a value. When you're working with large amounts of data, making API calls, or manipulating your data in intensive ways, this can be a very powerful tool. 