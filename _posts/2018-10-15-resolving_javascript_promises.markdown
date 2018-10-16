---
layout: post
title:      "Resolving Javascript: Promises"
date:       2018-10-15 21:03:38 -0400
permalink:  resolving_javascript_promises
---


<p>Let's jump right in. What is a promise? Well, it looks something like this code:</p>

```
var promise = new Promise(function(resolve, reject) {
// some async action
  if (/* no errors */) {
    resolve("Request has been resolved.");
  }
  else {
    reject(Error("Rejection is harsh"));
  }
});
```

<p>Now some definition and terminology: A promise is an object that may produce a value, some time in the future. Of note is that promises allow for a synchronous handling of an asychronous action, such as api calls. The value returned may be a *resolved* value, or a *rejected* value (the cause of the rejection, such an an error). These returned values can then be handled by callback functions. Have you ever seen a `.then`? Stuff like that. </p>

<p>A promise has 3 possible "states". </p>
1. It may be *fulfilled*. <br/>
2. It may be *rejected*. <br />
3. It may be *pending*.  <br />

<p>Once a promise has been either fulfilled or rejected (note: not pending), then the promise is considered *settled*. This is similar to the notion of 'settling a score'; the promise/repayment being fulfilled will settle the debt, just for sake of analogy.</p>

<p>Let's make sure we understand the typical steps involved. A new Promise can be instantiated, with a callback function. The callback takes two parameters: resolve and reject. If the execution goes well, resolve() is called. If it does not go well, reject() is called. Let's see an exmaple: </p>

```
const promise = createNewUserAsynchronously(userInfo); 
promise.then(successCallback, failureCallback);
```
and according to MDN documentation, this can be short handed into: 
`
createNewUserAsynchronously(userInfo.then(successCallback, failureCallback);
`

<p>Therein the successCallback or failureCallback could be a .then or .catch, respectively. These can be chained, but that's another topic worth reading up about! Ok, let's close off by providing a classic final example, just in case this stuff hasn't clicked just quite yet. </p>

```
let somePromise = new Promise((resolve, reject) => {
  // calls resolve() when async successful or calls reject() when async fails.
  // To simulate: setTimeout(...) mimics async nature of something like an API call. 
  setTimeout(function(){
    resolve("World!"); // simulate when async succeeds
  }, 5000);
});

somePromise.then((successGreeting) => {
  console.log("Hello, " + successGreeting);
});
```

Run the above code in your browser dev tools console (press F12). After you see the console log, go ahead and type in somePromise then press enter again. Notice a difference? If done correctly, the output should look like this: 
```
Promise {<pending>}
VM102:10 Hello, World!
somePromise
Promise {<resolved>: "World!"}
```
We can see the intial call was labeled pending state, but after success, the callback .then logs our message. Moreover, when we call somePromise again, it has its label as resolved already. Did I mention a promise can only be settled once? Pretty cool to see the basics all come together.


<p>Resources:
<br />
https://developers.google.com/web/fundamentals/primers/promises
<br/>
https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261 
<br />
https://kosamari.com/notes/the-promise-of-a-burger-party
<br/>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise
<br/>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises
</p>
