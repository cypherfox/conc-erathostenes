# conc-erathostenes
A concurrent implementation of the sieve of erathostenes in golang

In the Medium article [How Fast Is Golang?](https://medium.com/swlh/how-fast-is-golang-135c658205eb), 
Author 8F3E presents a golang implementation of the Sieve of Eratosthenes to compare the execution 
speed of Python and Golang. The implementation focuses on reability and speed of execution to a 
certain extend, as appropriate to the subject of the article.

But this got me wondering, as the benchmark is run to 100k for a limit on the sieve, that this implementation
would require a memory requirement of O(n), while the number of primes can be approximated as x/log(x), 
thus O(log(n)) (see https://people.mpim-bonn.mpg.de/zagier/files/doi/10.1007/BF03039306/fulltext.pdf)

This repo represents a sieve implementation that focuses on two elements:

* reduce memory requirement
* support concurrent operation to utilize multiple cores if available.
