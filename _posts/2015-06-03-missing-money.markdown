---
layout: post
title: "Problem of the Day: 2015-05-28"
date: 2015-06-03 11:13:00
categories: problemoftheday
---

## Problem  
### Missing Money [problemotd.com/problem/missing-money][potd]
Two brothers, John and Dom, set up an apple stand outside their parent's house. Each sells thirty apples a day. John sells his apples at two for 50 cents (and therefore earns $7.50 per day). Dom sells his apples at three for 50 cents (and therefore earns $5.00 per day). Thus, the total received by the brothers is $12.50.

One day, John is sick, and Dom takes over his apple selling duties. To accommodate the differing rates, Dom sells the 60 apples at five for a dollar. But selling 60 apples at five for a dollar yields only $12.00 earnings at the end of the day. What happened to the other 50 cents?
## Solution
No code required, this is pretty basic math. Dom earns less money because (1/4 + 1/6)/2 != 1/5
{% highlight java %}
//Normal days
(30 x 1/4) + (30 x 1/6)
= 30/4 + 30/6
= 90/12 + 60/12
= 150/12
= 12.5
//Sick day
60 x 1/5
= 12
{% endhighlight %}

[potd]: http://www.problemotd.com/problem/missing-money/
