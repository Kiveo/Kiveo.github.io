---
layout: post
title:      "Rails with Jquery"
date:       2018-08-29 03:21:39 +0000
permalink:  rails_with_jquery
---


<p>I modified the rails app, Flight Lesson Tracker, to have additional features reliant on js and Jquery. The requirements of the project were well laid out: </p>
<p>Rails with jQuery Specs:</p>

```
[X] Use jQuery for implementing new requirements

[X] Include a show resource rendered using jQuery and an Active Model Serialization JSON backend.

[X] Include an index resource rendered using jQuery and an Active Model Serialization JSON backend.

[X] Include at least one has_many relationship in information rendered via JSON and appended to the DOM.

[X] Use your Rails API and a form to create a resource and render the response without a page refresh.

[X] Translate JSON responses into js model objects.

[X] At least one of the js model objects must have at least one method added by your code to the prototype. Confirm
```

<p>The features themselves were, of course, specific to my application. These are more simply stated as the following features: </p>

> * JS functionality added onto a git branch:
> * Ajax calls and displays "Next" and "Previous" lessons from a singular lesson view. 
> * Ajax calls and displays an instructor specific index of lessons from the Dashboard view. 
> * Ajax calls and displays a new student name and message from the new student create page. 

<p>The bullet points certainly make it seem like this was a quick and easy project. Unfortunately, it was not quick and easy. However, that was a good thing, as it turns out. Either way, I opted not to rebuild the controllers to only handle json and api endpoints. Instead, I overlayed the ajax functionality by using respond_to html/json logic into the controllers. I also added a gem and some code to make quick work of serializers.</p>
<p>The project was entertaining and enlightening. I found myself working toward code that I wanted, more than along the lines of code from school examples or videos. That was both super frustrating and very fruitful, in the long run. I feel I know much more about the dynamic interactions and testing them than I did before. </p>
<p>I want to continue to develop the Flight Lesson Tracker in the future and make it significantly better looking and functioning than it is now, but overall I am happy with it! I was even able to discover and fix a bug in my app while I extended the ajax functionality. Time for a well-earned break! Happy coding, everyone.</p>

