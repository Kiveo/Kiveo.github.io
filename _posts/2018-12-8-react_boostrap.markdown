---
layout: post
title: "React with Bootstrap 4"
date:       2018-12-07 00:30:00 +0000
permalink:  react_bootstrap_4
excerpt: "Many companies are seeking developers practiced with Bootstrap, which is no surprise. Apparently, there is a large push for transitioning to Bootstrap 4, specifically. Reactjs is also in high demand. After some searching, evidently there is a react-strap npm package, but it uses BS3. Hm. Time to figure out how to use Bootstrap 4 within a React app!"
---
 
After viewing several job postings, I noticed an interesting trend. Many companies are seeking developers practiced with Bootstrap, which is no surprise. Apparently, there is a large push for transitioning to Bootstrap 4, specifically. Reactjs is also in high demand. After some searching, evidently there is a react-strap npm package, but it uses BS3. Hm. Time to figure out how to use Bootstrap 4 within a React app!

As with any skill, things come with practice and time. However, we don't exactly have time to spend months practicing every bootstrap 4 (henceforth, BS4) class combination. Nor will a blog do any justice to becoming proficient in React. As with most of my posts, we will be taking a high-level approach! The plan is to use some samples from the BS4 website, integrate them into a simple React app, and discuss a generic approach to integration.

Let's get started! First off, make sure you head to the [Bootstrap 4 website](https://getbootstrap.com/docs/4.0/getting-started/introduction), which is also in my sources below. They provide excellent instructions for getting started. I should note: I am presuming any interested readers are familiar with Reactjs, but if you're looking to code along, feel free to use 'create-react-app' and add code accordingly. So, we need to import the associated files so we can actually use Boostrap within our application.

1. Visit the BS4 website and copy their CSS + JS imports. 
2. Link the stylesheet into your index.html file's <head>.
3. Add the BS4 script tags into your index.html file's body (just before the closing tag: </body>)

Here is the code! Easy enough, yea? 
~~~~
  <!-- BOOTSTRAP 4 CSS LINK: put within <head> -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

  <!-- BOOTSTRAP JS FILES: place just above closing </body> tag -->
  <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>
~~~~

Let's touch upon a couple of important notes. The js files are actually optional! That said, if you're using a React app and planning on a js free website... well you're either super disciplined, or barking up the wrong tree. Still, it's worth mentioning. On that note, the js files are actually supposed to be imported in order: Jquery, Popper, and then Bootstrap. I'm no expert and their documentation says so. Thus, I do so. (I presume if they load async, BS might actually call some Jquery method and KABOOM! ...Erorrs). As a final note about the files, there is a list of features bootstrap leans on for the javascript functionality. Here, I'll save you the effort of looking yourself:  

Bootstrap  4: Components reliant upon JS  
1. Alerts for dismissing
2. Buttons for toggling states and checkbox/radio functionality
3. Carousel for all slide behaviors, controls, and indicators
4. Collapse for toggling visibility of content
5. Dropdowns for displaying and positioning (also requires Popper.js)
6. Modals for displaying, positioning, and scroll behavior
7. Navbar for extending our Collapse plugin to implement responsive behavior
8. Tooltips and popovers for displaying and positioning (also requires Popper.js)
9. Scrollspy for scroll behavior and navigation updates

Per my usual, I must mention another caveat: I am not trying to discuss how to simply use 'classes' from BS4, as that's a matter of simply typing the React className="col-md-4" etc. We want to leverage the POWAH of BS4 and steal-er...I mean, mimic their useful component-like features. This is React afterall!  
Moving on! Now we get to the fun stuff. Let's take a sample for a test drive. We will start with a 'J-U-M-B-O TRON!'. That was fun to type, actually. Navigate the BS4 page for Components > Jumbotron. 

Go ahead and create a Jumbotron component (or container, like my example below). You can type it out by hand however you prefer your components, you can use my sample, OR you can do what I did initially. What's that? STEALLLL--err, *ahem* copy one of the bootstrap samples on their website. They put it there for us. Don't feel guitly. Do it.  

>>Pro Tip: Open your dev tools(F12),  
>>inspect(CNTRL+Shift+C) the most parent element of the component you're interested in, and then right click it.  
>>Select the option 'Edit as Html'. That open a mini frame like window where pressing Select All (CNTRL + A) will copy only the pertinent html.  
>>You're welcome.

Ok, once you've *acquired* the basic html/code for the component, paste or save it into your component file. Of course, adhere to React's insistance on wrapping components into a parent element (Would you like a Div for your Div? Here's React!). Now to do some money laundering **ahem*, some code cleanup. Your code *most likely* will include some not-so-React-friendly snippets in it, if you've used my method of acquisition. (Btw, I already cleaned my sample codes below, in case you ripped me off.. yw again!).  
So what do I mean? Well, as you may recall, React components usually don't use things like `<a>` all that often. Not directly anyway. Had we begun our example with a Navbar, for sake of argument, we'd definitely want to change those `<a>` tags!

Instead of telling you every possible adjustment OR only talking about the Jumbotron, I will list the most common issues I had. I'll even include the most *sneaky* little error I ran across.

1. You may get an error that you can't quite figure out. Something about not using a specific type of element...that you KNOW you can use with React. Something like an `<image>`, `<hr>`, or even an `<input>`. Check the code and add the self closing tag. The subtle difference between `<image>` and `<image />` goes a long way here!
2. Change *class* to be React's *className* attribute
3. Especially if you're using react-router-dom or navigation, change `<a>` tags to `<Link>`... better yet: use `<NavLink>`
4. Convert *href* into '*to*' for use with Link in React 
5. React doesn't play nicely with BS4's insistence on using `<a>` with role="button". Save the headache, convert to button.
6. You don't need to apply *.container* to every div, IAW BS4 docs: it trickles down. Bear in mind when calling components.
7. Don't be afraid to make a css file for your component...Bootstrap is great but it often needs tweaking. Definitely read their documentation. I know we are riffing a lot, but we can't simply parrot. We need to understand what's cooking. Disclaimer made!

There are probably a couple I am forgetting, but I have faith in you! Just be sure to check the console for any messages. 

Here is a sample Jumbotron component, which uses props and class (might expand features later, hence the class vs function):
~~~~
  import React, { Component } from 'react';
  import './Jumbotron.css';

  class Jumbotron extends Component {
    render() {
      return(
        { <!-- The jumbotron-fluid can be removed if you don't want a full width jumbo --> }
        <div className="jumbotron jumbotron-fluid">
          { <!-- I used a container here because my app's jumbotron is imported outside of one. --> }
          <div className="container">
            <h1 className="display-2">{this.props.title}</h1>
            <p className="lead">{this.props.subtitle}</p>
          </div>
        </div>
      );
    }
  }

  export default Jumbotron;
~~~~

Alright, go ahead and npm start that baby up! If all goes well, you should have your very own jumbo-tron. Feel free to slap a background image on it to make it really shine. So, we took a component, adjusted it to fit within our React environment, and sat back to enjoy the show.  

I want to highlight the process: read the docs, follow their lead, make things React-ified, and test it out! Pretty simple. I encourage you to try it out with several components and use some react-router while you're at it. I personally rinse-repeated the process for a modal, jumbotron, fixed responsive navbar with dropdown and logo (the toughest), a sticky-footer (extra css required), and even some cards. I enjoyed the end result. Bootstrap and React are very powerful tools indeed.  

Bootstrap comes with a plethora of classes, so it will take time to instinctively use them all. Still, creating components is basically what React is all about, so I figured this would be a nice little overview of how I handled the more bulky side of BS4.    

This wraps up how we can leverage BS4 with React, without having to rely on an npm package. 

As always,  
Coffee and Code On, friends!


*SOURCES:*  
[Bootstrap 4](https://getbootstrap.com/docs/4.0/getting-started/introduction)  

[Create A New React App](https://reactjs.org/docs/create-a-new-react-app.html)

*Notes: I am not attempting to say that any packages pertaining to BS3 aren't still relevant. I am simply trying to provide an alternative approach. I found the process fun, intuitive, and a nice refresher on both frameworks*