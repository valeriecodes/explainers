---
layout: post
title:  "Recursion Basics"
date:   2017-04-21 10:30:28 -0500
categories: jekyll update
---

# Infinite Fun Without Infinite Loops

## What is recursion?
Solving a problem by solving smaller versions of the same problem. A recursive function is one that calls itself.

One mathematical practice that mirrors the structure of a recursive function is an inductive proof. If you've used this, a lot of these concepts may be familiar to you.

In an inductive proof, you can prove that something is true for all natural numbers _N_ by proving that:

* It is true for the first natural number (0 or 1) (this is called the **basis** or **base case**)
* It is true for arbitrary natural number _n_ and _n_ + 1 (this is called the **inductive step**)

By the same token, a recursive function has:

* A **base case**. This is a defined solution that will not call the function again. (This is where the function stops.)
* A **reduction step**. This relates the problem to a smaller subproblem of the same function. (Converges to the base case enventually)

### Fun with recursion

* The first P in PHP stands for PHP, PHP: Hypertext Preprocessor (https://en.wikipedia.org/wiki/PHP)
* The G in GNU stands for GNU, "GNU's not Unix" (https://en.wikipedia.org/wiki/GNU_Project)

Google easter egg:
![Recursion!]({{ site.url }}/assets/img/recursion.png)

Cute, right?

Let's think about writing a recursive program that performs a simple countdown.

What is the base case?
What is the reduction step?

### Method signature:
```
def countdown(n):
  # method body goes here
```

Want to use Python? Try [this](http://www.skulpt.org/).

### Desired output
```
>>> countdown(10)
10
9
8
7
6
5
4
3
2
1
BLASTOFF!
```

Go over the solutions together.

## Pitfalls

* Make sure that you have a base case and that you will always hit it. Otherwise the program will loop infinitely.
  * What's wrong here?
  ```
    def countdown(n):
      if n == 0:
        print "BLASTOFF!"
      else:
        print n
        countdown(n-1)
  ```
* Make sure that your problem is actually getting smaller each time.

## Next problem: Factorial
[Remember these?](https://en.wikipedia.org/wiki/Factorial)
> 3! = 3 * 2 * 1

> 5! = 5 * 4 * 3 * 2 * 1

And so on...

Let's write it.
What is the base case?
What is the reduction step?

### Method signature:
```
def factorial(n):
  # method body goes here
```

Spend 10 minutes on this. Let's not worry about negative numbers for now.
[Need that site again?](http://www.skulpt.org/)

### Desired output
```
>>> factorial(5)
120
```

## Next up: Fibonacci Sequence
![Fibonacci Sequence formula](http://www.roulette-systems.org/wp-content/uploads/2012/06/fibonacciformula.jpg)

Write a function that returns the nth Fibonacci number.
Base case? Reduction step?

### Method signature:
```
def fibonacci(n):
  # method body goes here
```

Remember: `fibonacci(0)` is 0 and `fibonacci(1)` is 1

Let's spend 10 minutes on this.

### Desired output
```
>>> fibonacci(6)
8
```

What about really big inputs?

Other pitfalls

* Redundant calculations
* Stack overflows (it's not just a website!)

## Binary search
Given a sorted array and a number, write a recursive function that returns true if the number is in the array and false if not.

Base case? Reduction step?

### Method signature:
```
def search(arr, n):
  # method body goes here
```

15 minutes to work.

### Desired output
```
>>> search([1, 2, 3], 3)
True
>>> search([1, 2, 3], 5)
False
```

Other things to know:
* Iterative approaches
* Memoization/dynamic programming

Iteration in mathematics may refer to the process of iterating a function i.e. applying a function repeatedly, using the output from one iteration as the input to the next.

Recursive functions are often easier to write with iteration. Simply put, an iteration is a for-loop.

### Countdown program in iterative form
```
def countdown(n):
  for i in range(n, 0, -1):
    print i
  print 'BLASTOFF!'
```

Exercise if we have time: rewrite previous functions with iteration.

Resources:

[Princeton lesson on Recursion](http://introcs.cs.princeton.edu/java/23recursion/)

[Wikipedia page on recursion](https://en.wikipedia.org/wiki/Recursion_(computer_science))

[Khan Academy lesson on recursion](https://www.khanacademy.org/computing/computer-science/algorithms/recursive-algorithms/a/recursion)

[Wikipedia page on mathematical induction](https://en.wikipedia.org/wiki/Mathematical_induction)
