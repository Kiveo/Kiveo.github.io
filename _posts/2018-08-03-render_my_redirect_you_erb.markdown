---
layout: post
title:      "Render my Redirect, you ERB!"
date:       2018-08-03 11:13:27 -0400
permalink:  render_my_redirect_you_erb
---


<p>One of the better methods to understand a concept is to read about it. It's even better to write about it. Let's do both. So, I came across a few articles (mainly specific to rails and a bit dated). One article, written in 2012, took aim at the difference between Redirect and Render (http://zackshapiro.com/post/33095402045/beginners-guide-to-redirect-and-render-in-rails). The most concise take away from Mr. Shapiro's article, for me, was the following: </p>
> With a Redirect, Rails tells the browser to do a new HTTP request to that specific path. Your code stops running while your browser pushes you to a new page. With Render, you can load many different pieces of your view, from partials and error messages to forms or even entire pages, like a 404 error page.
<p>I liked the mention of render affording the flexibility to use many different resources, such as error messages. Though, I felt the article was a bit too shallow in scope, likely because he wrote it as a "beginner's guide". I also knew it was technically possible to transmit an error message using a redirect, as I had done so about ten minutes earlier as I did a project review. So, that leaves some grey area, doesn't it?</p>
<p>I found another article where the author speaks about a more specific example he actually had and what helped him figure out a problem. Nothing teaches a lesson quite like experience, eh? Though, clearly, not an official source, I found a couple of his statements pretty interesting. He is pretty specific, when he says,</p> 
> "when you successfully store data you want to respond with an HTML redirect. That will force the browser to start a new request."
<p>The author goes on to explain how he and others can pass params data between pages/controllers via passing variables to renders. The article can be found at: https://gustavocguimaraes.wordpress.com/tag/render-vs-redirect_to/. </p>
<p>Ok, that's a good start. I decided to dig a bit deeper because I needed to resolve the mental issue I had with 1. Knowing redirects should create new requests without instance variables and 2. Knowing I was able to create a page change via redirect that displayed an error message. The next two articles I found were enlightening. The first, because it answered the question bluntly. (Spoiler: Because I used Flash). The second, because the author was not only the same as the second article we found, but it also turns out he is a fellow alumni of Flatiron school! This place is just awesome. Anyway, let's hit the last two revelations quickly.</p>
<p>First, A stack overflow question and answer (I know, I know...the endless void of half learning). Within the problem/answer messages, I found this gem: "The flash hash persists for exactly one redirect or render. So you should be fine with the default settings.". Bingo! That's how I was able to pass my error message (technically flash[:message]) while using a redirect. Nice. The other page, written by Gustavo, includes a good block of code for us readers to review for a use case scenario. Disclosure, I have added comments to highlight the topics discussed.</p>
```
def create
    @user = User.new(params[:user])                                   #Variable can be dropped or carried, render vs redirect
    if @user.save
      sign_in @user   
      flash[:success] = "Welcome to Gentle Reminder"  #FLASH PERSISTENCE/MESSAGE FOR THE REDIRECT
       redirect_to new_user_goal_path(@user)                 #REDIRECT 
    else
      render "new"                                                                        #RENDER if signup failed
    end
  end
```
<p>At this point, I think we get the idea. I did find one last good piece worth mentioning, at stackoverflow: "So the place where redirect_to should be used is when you're doing a HTTP POST request and you don't want the user to resubmit the request when it's done (which may cause duplicate items and other problems)." Good advice. This should cover the basics, if anyone wants to read a good and in depth guide on the subject of render vs redirect, reference the following link.</p>
<p>https://gist.github.com/jcasimir/1210155</p>

