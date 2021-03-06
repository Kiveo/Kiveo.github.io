---
layout: post
title: "Destructuring"
date:       2019-01-05 00:30:00 +0000
permalink:  destructuring
excerpt: "Destructuring is one of the topics in coding that isn't often spoken about. New coders will see destructuring done by more seasoned devs and have an immediate reaction. Feelings of confusion, apprehension, or joy can result. Some people love destructuring as a means to simplify code. Others might argue it is not explicit enough, especially once another developer has a look at your code. Let's take a look at some of the stuff surrounding destructuring and let the reader decide if they want to use it."
---
 
Destructuring is one of the topics in coding that isn't often spoken about. New coders will see destructuring done by more seasoned developers and have an immediate reaction. Feelings of confusion, apprehension, or joy can result. Some people love destructuring as a means to simplify code. Others might argue it is not explicit enough, especially once another developer has a look at your code. Let's take a look at some of the stuff surrounding destructuring and let the reader decide if they want to use it.  

Destructuring assignment is a term that seems almost an oxymoron. Let's take a look at an official example from the MDN. I have added line numbers for reference.  

>"The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables." -MDN 

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
>The object and array literal expressions provide an easy way to create ad hoc packages of data.
~~~
var x = [1, 2, 3, 4, 5];
~~~
>The destructuring assignment uses similar syntax, but on the left-hand side of the assignment to define what values to unpack from the sourced variable. - MDN

So what's going on here? We know that the expression on line 1 is basically an array assignment of the values a(10) and b(20). The example goes on to print the values of a and b to the console. 

We see what appears to be another array assignment with an added on '...rest' variable (line 9). Those 3 variables are then assigned the values of 10, 20, 30, 40, and 50. Wait. How are three variables being assigned to 5 values? If you already know, then well done. For any who might not: that "..." is the array/object spread operator. On that note, much of destructuring is about array and/or objects, so you'll be seeing a lot of the spread operator. You'll probably be using a lot of it too, if not already. [Spread Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

Ok, back to the initial example. We took an array of values, using a spread operator, and implicitly assigned multiple values to the third variable "rest". We assigned values and destructured at the same time. Yea, try not to think too hard about destructuring assignment. I recommend just seeing it as an extension of the spread operator.  

Let's dive more into the destructuring! The above will make more sense after this. First, we go into array destructuring.

Basic Variable Assignment
~~~
let sample = ['hello', 'world'];

let [one, two] = sample;
console.log(one); // "hello"
console.log(two); // "world"
~~~

In the above example, we create a sample variable and give it a value of the hello world array. We then destructure by creating namespace-like variables('one' and 'two') and assigning them to the array 'sample'. That's the basic magic of destructuring. This syntax will auto-magically assign 'one' (variable name doesn't matter) to be the first value of the assigned array. Naturally, the sequence continues with 'two' being assigned the next value of the array, world. That is the basics of array destructuring.

Next up, Object destructuring. Let's look at an example:

~~~
const pet = {
  name: 'Stitch',
  age: 5,
  owner: 'Lilo',
  food-type: 'omnivore',
  species: 'alien',
  debut: 'movie'
};

//pre ES6 format
const name = pet.name;
const age = pet.age;
//etc
~~~

We see that we have an object, pet. The pet's attributes can be assigned to variables by using the 'object.attribute' format. However, destructuring allows us to assign multiple attributes to values all at once and simplify the process.

~~~
const { name, age, owner } = pet
console.log(name) //expect name === pet.name
~~~

The code above will assign the variables (name, age, owner) to the pet's attributes of pet.name, pet.age, and pet.owner. Then, we can access them directly, similar to before but the assignment process is more streamlined. Unlike arrays, the name of the variable does matter and will access the associated attribute. Pretty cool stuff.

Destructuring gets a bit more complicated and really has some great power to it. There are many more examples on the MDN and across the web, but these are the basics. I've included links to some sources that may prove useful. For now, after reviewing the spread operator and the basic examples of destructuring, take a look at the first example of this blog post. I'll bet it makes more sense now!

~ Coffee and Code on ~

*SOURCES:*  
[MDN Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)  
[Moz Hacks Blog](https://hacks.mozilla.org/2015/05/es6-in-depth-destructuring/)
[Wesbos Blog](https://wesbos.com/destructuring-objects/)


*Notes: I recommend playing around on the command line using node's REPL or whatever javascript environment you prefer. Try making an object or array and then using destructuring to access the values/attributes. It is something any developer should become very familiar with! Feel free to use my Lilo and Stitch example =)*