---
layout: post
title:      "React + Redux: Aviation-Client web app"
date:       2018-10-11 08:59:01 +0000
permalink:  react_redux_aviation-client_web_app
---


<p>I began work on my first React and Redux front end client, which was powered by a Ruby on Rails backend API. The endeavor was a tad intimidating at first. The hardest part, for sure, was starting. How would I connect the front end to the back end? Should I use a Rails API based in default sqlite or plan ahead for Heroku deployment using PostgreSQL? I ended up creating two local git repos, separate from each other. One file structure for the Rails API and a different one for the React front-end. Oh, and I opted for PostgreSQL, as I plan to load the web app (called Aviation-Client) to Heroku eventually.</p>
![](http://i1044.photobucket.com/albums/b446/mrtesini/20160713002241_zpsb6tmtipp.jpg)
<p>The concepts were loosely in my mind, but as I spent dozens of hours testing my code on the local server, I began to really feel a sense of mastery over "what" Redux really was. React was a fairly simple pill to swallow, no more difficult than Rails, anyway. However, Redux seemed beastly in comparison...from a mental challenge standpoint. It started as a "why SO much extra work?!" thought process to eventually an understanding that "this would really help in a gigantic application, where components numbered in the hundreds or more". Making asychronous calls proved to be an interesting challenge, due to the nature of javascript. That said, middleware and "thunk" made the process a lot less painful.</p>

<p>React router was another fun endeavor. It boiled down to mimicking rails RESTful navigation, while in some cases never even pinging the backend server... t'was pretty cool.</p>

<p>There was much more coding and setup (boilerplate, I think the coder term is) than I was accustomed to writing when it came to Redux, especially. That said, seeing the project come together and instantly update components/state was very satisfying. The application never uses a page refresh. I feel pretty positive about being able to say I can now build applications that never need to reload.</p>

<p>I will be posting the application online, after I am satisfied with  augmentations I plan to do. These range from improved form validations to enable user authentication. For now, I am content with it's appearance and functionality, as a showcase of baseline coding ability.</p>

<p>Github Repo for REACT/Redux: https://github.com/Kiveo/aviation-client </p>
<p>Github Repo for Rails API: https://github.com/Kiveo/rails-api </p>
 
<p>Thanks for reading, </p>
<p>  -Mav </p>
