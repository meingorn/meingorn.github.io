---
layout: post
title:  "Quicksort: It's Quick"
date:   2017-06-30 18:51:41 +0000
---



Following up with last week’s blog post, we’ll cover another “divide and conquer” recursive algorithm, quicksort. Like merge sort, quick sort generally has O(nlogn) efficiency (however, worst case it can have O(n^2) efficiency). It is considered less ‘stable’ than merge sort, meaning it’s not going to reorder elements with identical keys. If you have a well-implemented quicksort, it can be the fastest sorting algorithm. However, you have to be weary of data quality lest you end up with a O(n^2) efficiency implementation. 
 
The basic premise of quicksort is to sort an array by choosing a pivot element in the array and sort by comparing the element to a subarray via a partition. Similar to merge sort, we break down the sorting on the left and right sides of the pivot into subproblems to be solved in parts. However unlike merge sort, we do not need to create a new array to keep track of them, we simply need to keep track of the start and end points of each subarray.  Here’s a visual from[ this video](https://www.youtube.com/watch?v=COk73cpQbFQ): 
 
![](http://imgur.com/7vElURv.jpg)
 
Which after running becomes: 
 
![](http://imgur.com/03ewVLi.jpg)
 
If that still doesn’t make sense after this blog post, I’d highly recommend checking out the video. He does a very thorough job of explaining how it runs. If you’ll notice, there’s pseudocode on the lefthand side which explains the logic we’ve laid out, adding an if-statement to make sure the recursion ends once the start index of the array is no longer less than the end index - or simply put there is only one element in the array(or any other edge-cases that may come up). 
 
So the two main decisions we need to make are: how do we pick a pivot point and how do we develop the partition logic? 
 
For the first one, stack overflow tells me that we want to get as close to a random pivot as possible to reduce the chances of getting an O(n^2) runtime. More on why that’s bad [here](https://stackoverflow.com/questions/164163/quicksort-choosing-the-pivot). Ultimately, you want your two subarrays to be broken up as close to the middle as possible so that we don’t have one side doing all the work (thus increasing the runtime). If we have a partially sorted array, it’s best to pick the number closest to the middle as a pivot. If you read the post, there’s a lot of discussion on how to do this and ultimately depends on your particular situation. For refactoring this code, check out the [median of three method](https://stackoverflow.com/questions/7559608/median-of-three-values-strategy). 


Next, we need to write our partition logic(JavaScript).
![](http://imgur.com/5ZFO6R4.jpg)
 
Finally, we write the quicksort functionality, which is simply recursive calls for the left and right parts of the array: 
 
![](http://imgur.com/EoFmZIy.jpg)
 
 
And let’s test it out: 
 
 ![](http://imgur.com/sLSyuRR.jpg)
 
 
Sources: 
http://blog.benoitvallon.com/sorting-algorithms-in-javascript/the-quicksort-algorithm/  
https://www.nczonline.net/blog/2012/11/27/computer-science-in-javascript-quicksort/
https://gist.github.com/paullewis/1981455 
https://stackoverflow.com/questions/5185864/javascript-quicksort
https://stackoverflow.com/questions/1933759/when-is-each-sorting-algorithm-used 
https://rawgit.com/escherba/algorithms-in-javascript/master/src/quickmiddle-sort.js 

