---
layout: post
title:  "Javascript’s ‘This’: Further Reading"
date:   2017-06-18 12:04:15 -0400
---

 
In JavaScript, ‘this’ is often referred to as one of the more complex concepts out there. I’ve been meaning to read up on why for a while, since I knew it’s important. Heck, there’s an entire You Don’t Know JS book written on the topic. [http://shop.oreilly.com/product/0636920033738.do] 
 
When breezily reading, I kept thinking, ‘this’ is execution context, it’s that simple. Looking back, this was one of the first times I was exposed to “this”: Simple, right? 
 
 ![](http://imgur.com/3nXuIiy.jpg)
 
Simple, right? Here we create a Sandwich class (forgive the lack of ES6 syntax and lack of disgust at using class syntax with JavaScript), defining each instance’s attributes with this. Now, when we create grilledCheese, passing in each value to be assigned to that object’s key, so if we called grilledCheese.breadType, we’d get “white”. The value for each attribute was assigned via ‘this’s execution contect at the moment Sandwich was called. 
 
Some other ‘this’ basics: if we’re referencing something in the global scope, we’re referring to the ‘window’ object via your browser’s DOM. However, if you’re in JavaScript’s ‘strict mode’, which turns of some of it’s ‘magic’ like type-coersion, ‘this’ would be undefined. The functions call() and apply() invoke a function with an explicit ‘this’ value, which can come in handy. 
 
In general, there are four ways ‘this’ takes a value: function calls, within methods on object, within an object that has been constructed, a function invoked with call, apply, or bind. Inside of a method, ‘this’ is the object that is attached to it, as soon as it is attached to some function this changes and becomes attached to the window. 
There are a couple of ‘gotchas’ working with modern JavaScript. This first, is the issue of lack of lexical scope in pre-es6 JavaScript. With the introduction of the arrow function, lexical scoping was added, which essentially means that it takes the ‘this’ value from the scope in which it was called. 
 
So this: 
![](http://imgur.com/V5aGXN1.jpg)
 
Becomes this: 
 
![](http://imgur.com/Ak6eYcr.jpg)
 
 
Further reading:
 
 
http://developer.telerik.com/featured/seven-javascript-quirks-i-wish-id-known-about/
http://bonsaiden.github.io/JavaScript-Garden/
http://www.quirksmode.org/js/this.html
http://stackoverflow.com/questions/3127429/how-does-the-this-keyword-work
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this
http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/
 

