---
layout: post
title: "Problem of the Day: 2015-06-01"
date: 2015-06-01 11:34:00
categories: problemoftheday java alwaysbecoding
---

## Problem  
### Minify Sum
Happy Monday!

Today's problem involves turning a long number in to a short number. The goal is to sum each digit of the number recursively until you reach a single digit. Here are a few test cases to make it easier to understand.

123456 = 1+2+3+4+5+6 = 2+1 = 3

99 = 9+9 = 1+8 = 9
## Solution
This is a quick and dirty solution. Converting the integer to an array of integers could/should  be refactored into a separate function, this conversion also proved to be the only somewhat tricky part.
{% highlight java %}
public int sum(int number) {
		if (Integer.toString(number).length() == 1) {
			return number;
		} else {
			String numberString = Integer.toString(number);
			int[] numberArray = new int[numberString.length()];
			for (int i = 0 ; i < numberString.length() ; i++) {
				numberArray[i] = (int) numberString.charAt(i) - '0';
			}
			int total = 0;
			for (int i = 0; i < numberArray.length ; i++) {
				total += numberArray[i];
			}
			return sum(total);
		}
	}
{% endhighlight %}

[potd]: http://www.problemotd.com/problem/minify-sum/
