---
layout: post
title: "Problem of the Day: 2015-06-04"
date: 2015-06-07 09:18:00
categories: problemoftheday java
---

## Problem  
### Pattern Finding [problemotd.com/problem/pattern-finding][potd]
We often solve fun number pattern riddles on here. Let's see if we can write a program to solve basic ones. Today's problem is to create a program that determines if an array contains an arithmetic or geometric sequence (no sorting required). Arithmetic patterns always change by the same value 2,4,6. Geometric patterns always change by the same ratio 8,4,2. If the pattern doesn't match either algorithm then just return "no pattern".

For bonus points figure out if a sequence has a plus 1 increase pattern (2,4,7,11).
## Solution
Fairly straightforward, I doubt this can be solved without looping over the list at least once.
{% highlight java %}
public boolean findArithmeticPattern(int[] a) {
	int d = a[1] - a[0];
	for (int i = 2; i < a.length; i++) {
		if(a[i]-a[i-1] != d) {
			return false;
		}
	}
	return true;
}

public boolean findGeometricPattern(int[] a) {
	int r = a[1]/a[0];
	for (int i = 2; i < a.length; i++) {
		if(a[i]/a[i-1] != r) {
			return false;
		}
	}
	return true;
}
{% endhighlight %}

[potd]: http://www.problemotd.com/problem/pattern-finding/
