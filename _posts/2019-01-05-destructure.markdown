---
layout: post
title: "Destructuring"
date:       2019-01-05 00:30:00 +0000
permalink:  destructuring
excerpt: "Destructuring is one of the topics in coding that isn't often spoken about. New coders will see destructuring done by more seasoned devs and have an immediate reaction. Feelings of confusion, apprehension, or joy can result. Some people love destructuring as a means to simplify code. Others might argue it is not explicit enough, especially once another developer has a look at your code. Let's take a look at some of the stuff surrounding destructuring and let the reader decide if they want to use it."
---
 
Destructuring is one of the topics in coding that isn't often spoken about. New coders will see destructuring done by more seasoned developers and have an immediate reaction. Feelings of confusion, apprehension, or joy can result. Some people love destructuring as a means to simplify code. Others might argue it is not explicit enough, especially once another developer has a look at your code. Let's take a look at some of the stuff surrounding destructuring and let the reader decide if they want to use it.  

Destructuring assignment is a term that seems almost an oxymoron. Let's take a look at an official example from the MDN. I have added line numbers for reference.  

>"The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables."

~~~
1 [a, b] = [10, 20];
2
3 console.log(a);
4 // expected output: 10
5
6 console.log(b);
7 // expected output: 20
8
9 [a, b, ...rest] = [10, 20, 30, 40, 50];
10
11 console.log(rest);
12 // expected output: [30,40,50]
~~~

Alright, so what's going on here? We know that the expression on line 1 is basically an array assignment of the values a(10) and b(20). Simple enough. The example goes on to print the values of a and b t the console. Ok, still simple. Then, we see what appears to be another array with an added on '...rest' variable. Those 3 variables are then assigned the values of 10, 20, 30, 40, and 50. Wait. How are three variables being assigned to 5 values? Good Question. 

~ Coffee and Code on ~

*SOURCES:*  
[MDN Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)  