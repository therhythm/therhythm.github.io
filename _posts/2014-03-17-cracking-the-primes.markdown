---
layout: post
title: "Problem of the Day: 2014-03-17"
date: 2014-03-17 12:00:00
categories: problemoftheday javascript alwaysbecoding
---

## Problem  
### Cracking The Primes
It's Monday! Hope you all had a good weekend and are set to solve this week's problems.  
One of the biggest areas in encryption is prime number generation. Eventually our computing power will grow to the point where RSA encryption will either need to be 1 million bits or a new key sharing standard will need to take over. In today's world a standard RSA key is 2048 bits. The key length is determined by the multiplication of 2 prime numbers, thus making it very hard to factor.  
For today's challenge I have multiplied two small prime numbers together. Your objective is to find the two factors used. The 48 bit key can be bruteforced in a reasonable amount of time whereas the 146 bit key may take some more time and smarter engineering. As always feel free to post any code used in cracking the numbers.  
Key (48 bit): 153728883468487  
Key (146 bit): 50134918426382971596395239206900954838888151
## Solution   
{% highlight javascript %}
(function crack(key) {
	var primes = [];
	var eratosthenes = function(limit) {
	    var sieve = new Array(limit);
		var results = [];
		sieve[0] = 0;
		sieve[1] = 1;
		for (var i = 2; i < limit; i++) {
		    ((i+1)%2) === 0 ? sieve[i] = 0: sieve[i] = 1;
		}
		for (var j = 2; j <= limit; j += 2) {
		    if(sieve[j]) {
		        for (var k = 2*(j+1); k <= limit; k += (j+1)) {
		            sieve[k-1] = 0;
		        }
		    }
		}
		for (var l = 1; l <= limit; l++) {
		    if(sieve[l] === 1) {
		        results.push(l+1);
		    }
		}
		return results;
	}
	var isPrime = function(number) {
	    var start = 2;
	    while (start <= Math.sqrt(number)) {
	        if (number % start++ < 1) return false;
	    }
	    return number > 1;
	}
	
	primes = eratosthenes(Math.ceil(Math.sqrt(key)));
	for (var i = 0; i < primes.length; i++) {
	    if(key%primes[i] === 0 && isPrime(key/primes[i])) {
	            console.log(primes[i] + ", " + key/primes[i]);
	    }
	}
})(153728883468487);
{% endhighlight %}

[potd]: http://www.problemotd.com/problem/cracking-the-primes/
