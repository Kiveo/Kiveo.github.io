---
layout: post
title: "React with Bootstrap 4"
date:       2018-12-07 00:30:00 +0000
permalink:  react_bootstrap_4
excerpt: "Many companies are seeking developers practiced with Bootstrap, which is no surprise. Apparently, there is a large push for transitioning to Bootstrap 4, specifically. Reactjs is also in high demand. After some searching, evidently there is a react-strap npm package, but it uses BS3. Hm. Time to figure out how to use Bootstrap 4 within a React app!"
---
 
After viewing several job postings, I noticed an interesting trend. Many companies are seeking developers practiced with Bootstrap, which is no surprise. Apparently, there is a large push for transitioning to Bootstrap 4, specifically. Reactjs is also in high demand. After some searching, evidently there is a react-strap npm package, but it uses BS3. Hm. Time to figure out how to use Bootstrap 4 within a React app!

As with any skill, things come with practice and time. However, we don't exactly have time to spend months practicing every bootstrap 4 (henceforth, BS4) class combination. Nor will a blog do any justice to becoming proficient in React. As with most of my posts, we will be taking a high-level approach! The plan is to use some samples from the BS4 website, integrate them into a simple React app, and discuss a generic approach to integration.

Let's get start! First off, make sure you head to the [Bootstrap 4 website](https://getbootstrap.com/docs/4.0/getting-started/introduction), which is also in my sources below.

Here is a sample Jumbotron component, which uses props and class (might expand features later, hence the class vs function):
~~~~
  import React, { Component } from 'react';
  import './Jumbotron.css';

  class Jumbotron extends Component {
    render() {
      return(
        <div className="jumbotron jumbotron-fluid">
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


This wraps up how we can leverage BS4 with React, without having to rely on an outdated package that only uses BS3. 

As always,  
Coffee and Code On, friends!


*SOURCES:*  
[Bootstrap 4](https://getbootstrap.com/docs/4.0/getting-started/introduction),  

*Notes: I am not trying to make the point that BS4 is better than BS3. I am also not attempting to say that any packages pertaining to BS3 aren't still relevant. I am simply trying to provide an alternative and demo one approach.*