---
layout: post
title:  "Understanding Merge Sort"
date:   2017-06-23 17:56:19 +0000
---

 
 
The other weekend I was troubleshooting an issue on a project with a friend with a CS degree, which was nice as my practical bootcamp knowledge complemented his more theoretical and thorough understanding of programming principles. After we fixed the issue, he offered to help out with my algorithm studies. I had recently spoken with him about banging my head over the recursive solution for the towers of hanoi problem (i think i’ve got it now!) we decided on another recursive algorithm: merge sort. We spent an hour or so on it, mostly talking about it conceptually, but being pretty wiped and short on time from the troubleshooting, we had to stop before finishing up. I’ve written this to help deepen my understanding of it. If you’re reading this, hopefully it’ll help you too. 
 
A brief overview of merge sort: as stated, it’s a divide and conquer algorithm - ‘divide and conquer’ being a paradigm based in recursion which breaks problems into subproblems, solves those subproblems via recursion, then once the subproblems are solved it is then able to resolve. LIke in this visual from Khan Academy: ![](https://ka-perseus-images.s3.amazonaws.com/db9d172fc33b90e905c1213b8cce660c228bb99c.png)
 
 
In the context of merge sort, we’re usually looking at an input of an unsorted array, so in this context merge sort divides the input into two halves, calls itself on each of the two halves until there are only two elements to compare, sorts those two elements, then continues to sort back up until there is one final sorted array. Wikipedia has a great visual: ![](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif ) 

 
The geeks for geeks youtube video (only a minute and 30 seconds long!) also has a clearer visual of it: 
<iframe width="560" height="315" src="https://www.youtube.com/embed/JSceec-wEyw" frameborder="0" allowfullscreen></iframe>
 
As the end of the video states, there are a couple of key features to the algorithm: First, we create a temporary array to store our elements in. Then, we write a function which compares the values of the element at the midpoint of each subarray via pointers, then uses a merge function to place the sorted elements into the new array. In this instance, I found the recursive aspect to be much simpler to follow than towers of hanoi mentally(maybe just used to it now?). One massive barrier to my original understanding and key to solving recursion, is that it functions similar to a heap, in that the last call of the function (in this case the call comparing only two elements) is the first to resolve, and that all of those other calls didn’t just disappear, they are waiting to be resolved in reverse order. 
 
In retrospect, I let my friend write out a custom complex visual aide for me over skype, with our only reference material being the Wikipedia page. I know now that googling an algorithm will give you lots of great pre-made content to explain it (sorry Trevor!). 
 
So, now that we hopefully understand how merge sort works conceptually, let’s implement it with JavaScript! I will be writing what is called the ‘top-down’ implementation: 
 
![](http://i.imgur.com/EYCreIY.jpg)
 
 
An important point on merge sort is that it has O(nlogn) efficiency, n being the number of inputs. Makes sense that it will take longer if there are more inputs, but the log factor has to do with how each recursive call is breaking it down into a tree, with logn referring to each level. For a more in-depth explanation see [this link](https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/a/analysis-of-merge-sort). 
 
Thanks for reading!
 


