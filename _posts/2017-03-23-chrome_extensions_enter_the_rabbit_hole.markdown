---
layout: post
title:  "Chrome Extensions: Enter the Rabbit Hole"
date:   2017-03-23 20:33:07 +0000
---


This past week we started doing some JavaScript here at Flatiron, something I’ve been looking forward to since day 1. One of the reasons that being good at JavaScript excites me is gaining the ability to make Chrome extensions. The ability to add an additional layer of interaction to the web is pretty exciting, and I’ve got about 1,000 ideas for fun and/or useful Chrome extensions (angel investors feel free to inquire via email). As it turns out, making a Chrome extension is surprisingly simple - thanks Google! In this post I’ll be walking you through the basic steps of getting set up to make an extension, as well as detailing my experience making my first one. 
	Google’s Chrome documentation has everything you need to get started. To summarize, a basic Chrome extension consists of four main files: manifest.json, icon.png, popup.html, and popup.js. Manifest.json includes all of the important metadata about your extension in (wait for it) JSON format. It’s crucial that you include a manifest version, name,  and version, otherwise your extension won’t run. Once that’s filled in you’ll need a .png file so that your extension is clickable and interactive in Chrome. Popup.html will come into play once someone clicks on your png, displaying information about your extension (see Adblock Plus’ example below). Popup.js provides the logic to render the content of the popup, as we can see below. 

![](http://imgur.com/UuMzoz7)

Step 1 - Get Setup
	Once these files are all set up, we can launch the extension in Chrome! First, visit chrome://extensions, then click the checkbox enabling developer mode, load the unpacked extension, and we’re done! Except, we haven’t actually done anything. Now is time for the actual fun part - building our idea!
For my first extension I wanted to keep things pretty simple: to make backgrounds of all web pages visited International Klein blue while the extension is enabled. I drew inspiration from two places on this one - 1st, an extension I have called Stylus that enables you to add to restyle any web pages - for example, I have one that makes my Github dark and spooky (and easier on the eyes.). International Klein Blue was developed by French artist Yves Klein’s work “Blue Monochrome” as “a means of evoking the immateriality and boundless of his own particular utopian vision of the world”*.

![](https://uploads1.wikiart.org/images/yves-klein/untitled-blue-monochrome-1959.jpg)
 
 The color was featured widely in his work, perhaps most famously in his work Blue Monochrome, which was a large canvas painted in nothing but IKB. As tribute, the name of the extension is called Blue MonoChrome.* 
	*So, on to the real question, how can we make this work? After a little digging I encountered content scripts, which are essentially JavaScript files that run in the context of web pages, using the DOM to read/alter them. All I had to do was add a section to manifest.json with my contentscripts details like so:*
	![](http://imgur.com/9K8dNqB)
	
As you’ll see, I added two files, one called blue.css and one called blue.js. My initial hope was that I could sneakily add a script that cleanly inserted the blue to all backgrounds. After a couple of failed attempts, I took a new approach and tried by simply altering the background property in blue.css: 
![](http://imgur.com/xom7I8w)

After reloading my extension, it worked! 
![](http://imgur.com/lndmnKe)

Success! Despite the atrocious user experience, I was pleased. However, in the end I didn’t end needing any JavaScript. I’m keeping the blue.js file there as a placeholder for future versions. Maybe one day I’ll make it user-friendly somehow?

Check out my code here:
https://github.com/meingorn/Blue_MonoChrome 

<iframe src="//giphy.com/embed/AVD4STcQQhkZO" width="480" height="297.7959183673469" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="http://giphy.com/gifs/michael-tobias-blue-myself-AVD4STcQQhkZO">via GIPHY</a></p>


Sources:
*https://www.moma.org/collection/works/80103 
https://developer.chrome.com/extensions/getstarted 
https://robots.thoughtbot.com/how-to-make-a-chrome-extension
https://github.com/StylishThemes/GitHub-Dark/tree/master/themes
https://chrome.google.com/webstore/detail/image-background-color/ocjaolenabdfhmpndkmnbojmjefdpago?hl=en
