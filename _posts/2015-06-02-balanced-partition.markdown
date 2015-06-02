---
layout: post
title: "Problem of the Day: 2015-06-02"
date: 2015-06-02 11:14:00
categories: problemoftheday java alwaysbecoding
---

## Problem  
### Balanced Partition [problemotd.com/problem/balanced-partition][potd]
Given a set of N integers, partition them in to two buckets such that |N1 - N2| is as small as possible where N1 and N2 are the sums of the partitions.
## Solution
There might be a proper algorithm out there to solve this. This is the naive solution I came up with, I'm not entirely sure this will work correctly with every input.
{% highlight java %}
public ArrayList<ArrayList<Integer>> balance(ArrayList<Integer> in) {
		//two buckets
		ArrayList<Integer> left = new ArrayList<Integer>(),
			right = new ArrayList<Integer>();
		ArrayList<ArrayList<Integer>> buckets =
			new ArrayList<ArrayList<Integer>>();

		//sort the integers in descending order
		in.sort(null);
		Collections.reverse(in);

		//put biggest integer in left bucket
		left.add(in.get(0));

		//loop over sorted integers,
		//add to left bucket if considered integer doesn't make
		//sum bigger than right
		//assuming best situation at every step
		for (int i = 1; i < in.size(); i++) {
			Integer consider = in.get(i);
			if (sumList(left) + consider < sumList(right)) {
				left.add(consider);
			} else {
				right.add(consider);
			}
		}

		buckets.add(left);
		buckets.add(right);
		return buckets;
	}
{% endhighlight %}

[potd]: http://www.problemotd.com/problem/balanced-partition/
