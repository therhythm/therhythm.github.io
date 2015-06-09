---
layout: post
title: "Problem of the Day: 2015-05-27"
date: 2015-06-09 15:29:00
categories: problemoftheday
---

## Problem  
### Odds And Evens [problemotd.com/problem/odds-and-evens][potd]
We have a fun math puzzle for today. Can you decipher the pattern and determine the next number in the sequence?

0, 0, 1, 2, 2, 4, 3, 6, 4, ?
## Solution
The title is a big hint that this is an alternating pattern. The odd numbers are counting up in increments of 1, the even numbers are 2 to the power of the previous number (or simply counting up increments of 2).
{% highlight java %}
0
 0 = 2^0
1
 2 = 2^1
2
 4 = 2^2
3
 6 = 2^3
4
 8 = 2^4
{% endhighlight %}

[potd]: http://www.problemotd.com/problem/odds-and-evens/
