---
layout: post
title:  "Object Equality in JavaScript"
date:   2017-04-11 14:43:26 +0000
---


In my early days of learning JavaScript I spent a great deal of time looking for the best book to read about JavaScript. I found that a lot of resources that were ‘in the know’ recommended Eloquent JavaScript, which I found extremely informative, if a bit dense for me to read carefully during the fast-paced bootcamp I’m currently enrolled in. In one of the first lines of Eloquent JS, the author derides an extremely well known book “JavaScript: The Good Parts” as too much oversimplification. The tone was so critical that I avoided ‘The Good Parts’ for a while, despite many recommending it to me. It took a developer friend of mine to pique my interest again when he put it to me like this: “it’s good to know the contents of in-depth books like ‘Eloquent’, but if you’re going to be a JavaScript developer you have to know ‘The Good Parts’ like the back of your hand”. So what do you know I started it up and quickly found a fun little idiosyncrasy that is now the topic of this post. 
	JavaScript makes a lot of assumptions, which is why it has access to strict mode where you can turn those parts off. In practice, this means that your code is often doing a lot of things that you don’t even think about as a newbie. For example, if you compare the integer 2 with ‘2’ (contained in a string) in your console, with the double equals sign, it will come back as true. What I didn’t realize as a noob was JavaScript was actually coercing the string into its integer value, and then comparing those, which is why triple equals comparison which lacks type coercion comes back false. 
	http://imgur.com/yeWyzOZ

‘JavaScript: The Good Parts’ queued me in on an even further aspect to be aware of, namely that not all type comparisons will be treated equally, specifically in this instance an object. In comparing two empty objects, it turns out that not only will it come back false for triple equals, but also double - why?
 
Turns out, that objects get treated a little differently than say strings or integers in JavaScript. When a new instance of an object is created, it gets its own unique place in memory. Each object created in the examples above are different instances. When comparing the values of two objects, what’s going on under the hood is the object is pointing us to its location in memory. Since each instance is saved in a different location in memory, when compared they are not equal. 
http://imgur.com/M4tGMlX

What happens if we need to compare values within objects whose contents should be equal though? A quick google search will tell you that there is no built-in way for us to compare objects, there are a few workarounds that we can employ. 
Lodash has a build in object comparison constructor: _.isEqual(object, other);
 
In ES5 we were also given Object.keys() which returns an array of a given object’s own enumerable properties(keys) in order. In ES7 we will have access to Object.values(), which does the same with the object’s values, so comparing objects with explicitly written functions will be far easier. Right now we can also use Object.is(val1, val2) to explicitly compare two values within an object. Until then, Stack Overflow my friend. 


Sources: 
Crockford, Douglas. JavaScript : The Good Parts. Sebastopol :O'Reilly, 2008. Print.
http://stackoverflow.com/questions/201183/how-to-determine-equality-for-two-javascript-objects 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is 
http://www.mattzeunert.com/2016/01/28/javascript-deep-equal.html 

