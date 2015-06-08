---
layout: post
title: "Problem of the Day: 2015-06-08"
date: 2015-06-08 11:15:00
categories: problemoftheday java
---

## Problem  
### Linked Stack [problemotd.com/problem/linked-stack][potd]
Happy Monday!

Today's problem is a classic data structures problem. The goal is to create a stack using a linked list as the backing structure. The stack should have a push and pop method implemented.
## Solution
{% highlight java %}
public class LinkedStack<Object> {

	private Node first;
	private int size;

	public boolean isEmpty() {
		return first == null;
	}

	public int getSize() {
		return size;
	}

	public void push(Object o) {
		Node oldFirst = first;
		first = new Node();
		first.setObject(o);
		first.setNext(oldFirst);
		size++;
	}

	public Object pop() {
		Object o = (Object) first.getObject();
		first = first.getNext();
		size--;
		return o;
	}

}

public class Node {

	private Object o;
	private Node next;

	public Object getObject() {
		return o;
	}
	public void setObject(Object o) {
		this.o = o;
	}
	public Node getNext() {
		return next;
	}
	public void setNext(Node next) {
		this.next = next;
	}

}
{% endhighlight %}

[potd]: http://www.problemotd.com/problem/linked-stack/
