---
layout: post
title: "Problem of the Day: 2014-03-11"
date: 2014-03-11 12:00:00
categories: problemoftheday javascript alwaysbecoding
---

## Problem  
### Palindromic Numbers [problemotd.com/problem/palindromic-numbers][potd]  
A palindromic number is a number that reads the same forwards as it does backwards. 123321 is a palindromic number where as 321321 is not. Negative numbers may be considered palindromic or not; it's up to you until someone proves otherwise.  
Your mission, should you choose to accept it, is to create a program to return whether a number is a palindromic number or not. To make things slightly more interesting you may not use a string or array in your solution. Thus doing something like "123.toString()" is not allowed.  
Good luck!  
## Solution  
### Cheat-y solution  
{% highlight javascript %}
(function palindromic(number) {
	var palindromic = false;
	var numberString = number.toString();
	var reverseString = numberString.split('').reverse().join('');
	if (reverseString === numberString) {
		palindromic = true;
	};
})(12321);
{% endhighlight %}
### Proper solution  
	Not yet solved.

[potd]: http://www.problemotd.com/problem/palindromic-numbers/
