---
layout: post
title:  "Heapsort in JavaScript"
date:   2017-07-08 18:33:16 +0000
---


In keeping with the recent theme of sorting algorithms, today we’ll be taking a look at Heapsort. Heapsort is a little different from the last two we looked at as it is based on the Binary Heap data structure. A Binary Heap is a complete binary tree (all levels except potentially the last are filled and all nodes as far left as possible).

![](http://imgur.com/RkbJRxz.jpg)

from : http://www.studytonight.com/data-structures/heap-sort

 A Binary Heap, then is a Complete Binary Tree where the nodes are sorted where each parent node is either smaller or larger than its child node (min and max heap respectively): 

![](http://imgur.com/rbJLzKK.jpg)

Also from:  http://www.studytonight.com/data-structures/heap-sort 

Heapsort involves two parts: first, build a max heap out of the input data, then sort each element into an array  by taking the largest element of the heap (the root) and inserting it into the heap repeatedly. 

This quick video has a great visual for how the logic works: 
<iframe width="560" height="315" src="https://www.youtube.com/embed/MtQL_ll5KhQ" frameborder="0" allowfullscreen></iframe>


If we’re implementing heapsort in JavaScript, the code will look like this:

First, we create the max heap. The logic breaks down pretty cleanly: we take in the array and node i which is its index in the array. If the left child is larger than the root, we set the left child as the new root and vice versa. Then, if we are not yet at the root we swap the elements and recursively heapify the result until we reach the root. 

![](http://imgur.com/FZFvBfv.jpg)


Next, we implement the actual heap sort. First we build the heap, then extract each element one by one from the heap, move the current root to the end, and call our heap making function on the reduced heap. 

![](http://imgur.com/VtOQdqA.jpg)


All together, our heapsort code looks like this: 

![](http://imgur.com/DDGIayN.jpg)

Some useful things to know: the time complexity for heapsort is O(nlogn). Heapsort is not as widely used as quicksort and mergesort because they are considered better inpractice. 

If you want a really in-depth explanation of the mechanics with a great explanation of the heap data type, this MIT lecture is great:

<iframe width="560" height="315" src="https://www.youtube.com/embed/B7hVxCmfPtM" frameborder="0" allowfullscreen></iframe>


Useful Links: 
* https://en.wikipedia.org/wiki/Heapsort
* http://www.studytonight.com/data-structures/heap-sort
* http://www.geeksforgeeks.org/heap-sort/



