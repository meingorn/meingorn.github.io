---
layout: post
title:  "Understanding “State” in JavaScript"
date:   2017-04-11 13:32:48 +0000
---



Recently at Flatiron my class has been delving into the basics of React.js. One of the first things you learn is that most things in the UI are broken into components, essentially pieces within your page that you can isolate from the page itself and reuse as necessary. This is one of the cool things about React, and it allows you to make dynamic web pages that can be modified quickly. Components are essentially JavaScript functions, and can take an argument of what is called a prop and return the React element describing what should render on the screen. 
	While ‘props’ were a little tricky for me to understand at first, they’re pretty easily understood as a way of passing a template that takes an input that will change the html accordingly, or more coherently: “a way of passing data from parent to child” (thanks docs!). Ok, makes sense. However, things got a little confusing when we got to state. In our early labs we were told to think of state as a prop that will be changed in the future. This explanation was enough to complete basic tasks like programming a simple image slider: 

![](http://imgur.com/fpXGhL9)

First we set the initial state in the constructor, in this case having the slider start at the first point in the slides index at currentSlidesIndex[0]. In the view, we allow the div to render dynamically based on the the current index without reloading the entire page. Seems like a pretty useful feature to say the least. 
	As I continued on informing myself about React, state seemed to keep coming up as a thing about React that was cool but confusing. Being attracted to useful quirks, I figured it would be good to look into. I quickly learned that Redux which I had often heard mentioned in the same breath as React. In the documentation, Redux is defined as a “predictable state container for JavaScript apps… it helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test. It became immediately clear that state was going to be a massive rabbit hole if Redux was created to help contain it, whatever that means. So my next goal became defining state in a way that was both simplified yet not so simple that I’m missing out on key concepts. 
	A simple definition I found on a post by Ryan Glover defines state as ‘how a component’s data looks at a given point in time’. So, as in our initial example, our photo slider changes how it looks based on the what index of our photos the user was currently on. This can get tricky if you have too many things using state, thus why it is advised that state be used sparingly and only once per component. If you look at the React Docs, they even advise that you write out all of your code first statically, coming back to write in state after the fact.
 It seemed as if most tutorials on the topic tried to boil down state as simply as possible, presumably in an effort to only give enough information to do what we need to do without getting tripped up by too much information. I have the tendency to go to deep before scaling back to where a reasonable person would need to be, so I took a stab at an in-depth article from reactkungfu.com, who generally have articles that are in-depth and at this point pretty incomprehensible to me. This particular post looks at the state source code. My goal: learn something cool about state that would be helpful to mastering it quickly. 
What I gathered was generally that when state changes occur, they are guaranteed to occur in order of execution, and will block other changes from being processed before the event is handled. There are some things that go on logically behind the scenes that are a little less clear, but more or less this is the final effect. 
Through my research, though there seems to be some complex things going on under the hood, I didn’t fully understand why state was so complicated that we needed a whole other technology to manage it. So I went over to our instructor Steven to see what he had to say. Basically, he said in a production-level website there are so many stateful components on a page that things can get extremely cluttered. In order to preserve the ‘single source of truth’ and make so many states more manageable, we have redux which in essence creates one large single state. Seems like I have reached the tip of a very hefty iceberg I look forward to mastering!

https://facebook.github.io/react/docs/state-and-lifecycle.html 
https://themeteorchef.com/tutorials/understanding-props-and-state-in-react
http://redux.js.org/ 
https://daveceddia.com/visual-guide-to-state-in-react/ 
http://reactkungfu.com/2016/03/dive-into-react-codebase-handling-state-changes/ 
http://imgur.com/fpXGhL9

