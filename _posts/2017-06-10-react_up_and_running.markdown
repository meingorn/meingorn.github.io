---
layout: post
title:  "React: Up and Running "
date:   2017-06-10 20:12:26 +0000
---

 
Well it’s been just over a month since graduating from Flatiron school and in that time it was great to work on my own site and start interviewing. My girlfriend and I had a voucher for a hotel in Mexico that we *had* to use before it expired, so I spent a couple of weeks beachside reading Tim Wu’s new book (get it!). Upon coming back though, working on my React/Redux site was a bit slow, so in the last week I’ve reviewed the fundamentals of React/Redux to get back into it. This post is meant as a guide/reference to get started on a React app for those who need a quick refresher. 
 
Environment setup
 
A typical React environment consists of Webpack(module bundler), Babel(JavaScript compiler), ES6(current JavaScript standard), NPM/Yarn(package manager), and React(duh). If this isn’t one of your first React apps, you can go ahead and build it from scratch as per[ this tutorial](https://scotch.io/tutorials/setup-a-react-environment-using-webpack-and-babel). However, at the moment setup can still be a little buggy. For that reason, as well as simply for convenience, many people simply opt for[ create-react-app](https://github.com/facebookincubator/create-react-app). For the ultra-lazy link-averse, you can get started on your own React app with two terminal commands(assuming you have npm or yarn installed): npm install -g create-react-app && create-react-app nameOfApp. Cd into that directory and boom, you’re done. The future is now. 
 
If you’ve gone through the initial setup process, your file tree should look like the following:
![](http://imgur.com/OZ3KOkm.jpg)
 
2. FUNdamentals
 
In the React documentation, it is described as a JavaScript library for building user interfaces - some might say the ‘V’ in MVC. Since we’ll be working towards integrating Redux in this post, we can also say that with the integration of the Redux and React/Redux libraries (no official affiliation with React at the moment), we’ll be building the entire MVC front-end out. React is especially cool for its use of what’s known as the virtual DOM. Basically, they’ve further abstracted out the browser’s DOM in order to create an interface the updates seamlessly.
 
 Most everything you see on the browser with React is a set of something called components put together. The React DOM updates the browser’s DOM to match any changes that happen in an individual component. Let’s take a closer look at the syntax in App.js, where we’ll be starting our work: 
 
![](http://imgur.com/OZ3KOkm.jpg)
 
First, we import our reference library, and what part of it we need, specifically Component in this case. Then, we import other files we’ll be referring to in that specific component. At first, this may seem a little cumbersome, but it’s actually a great way to keep things clean and stay on top of your code. It also speaks to another cool part of React - components aren’t communicating with each other unless we explicitly tell them to, which is one way that we are able to make things lightning fast. 
 
Next, we define our component, in this case App. App.js is a class-based component which uses ES6 syntax. Not all components need to be class-based. In fact, your component should only be class based if it needs to take in/maintain state (an important aspect of React that will be discussed shortly). If you find that your component is simply taking in some props (think properties, a React term which refers to the attributes you are passing into your component) and rendering, you can and should write your component with this syntax.
 
I’ll show you what this looks like then explain some things that may look weird to you: 
 
First we define our functional component like so, making sure to export it at the bottom so other parts of the app can find it: 
![](http://imgur.com/W98AQ29.jpg)
 
 
Then we import the functional component, calling it in the highlighted section with a syntax made for react called JSX (a combination of HTML and react). Two things to remember about JSX: your components should look like self-closing html and their name should be capitalized. 
![](http://imgur.com/8FrMzMb.jpg)
 
If we run npm install && npm start in our terminal, this will be rendered on the screen: 
![](http://imgur.com/pSEA5Pd.jpg)

 
So from here you can already do a lot if you are just trying to build a static page. However, what if we want to build something more ‘reactive’?
Badumch.gif
 
3. Introducing state
 
State is a JavaScript object used to render changes in components. Some things to know up front: never modify state directly via this.state.example = ‘bob’, always use the built in method setState ie. this.setState({example: ‘bob’}). Much can be said about state - in fact Redux’s primary purpose is to manage it - however, in order to illustrate its core use I’ll give an example of a search bar, taken from the fantastic React/Redux udemy course with Stephen Grider that I’d highly recommend. 
![](http://imgur.com/cYKxCwn.jpg)
 
Here we have a SearchBar component waiting for the user input. When the user types into the search bar, the component calls the onInputChange method, setting the state to the user’s input: 
![](http://imgur.com/A0ahUp2.jpg)

becomes...

![](http://imgur.com/CuJ8qiC.jpg)

From here, another blog post would be needed on the intricacies of state and best-practices. However, if you want to get up and running and make something simple in react, this is all you need. Some great resources I’d recommend to continue learning are Stephen’s course as I mentioned above and the Fullstack React book, and of course the React documentation, which does a great job of getting technical without being unreadable to a beginner. Also feel free to drop me a line if you have any React-related questions! 

