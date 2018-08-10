---
layout: post
title:      "Flight Lesson Tracker: a rails web app"
date:       2018-08-09 23:30:06 -0400
permalink:  flight_lesson_tracker_a_rails_web-app
---


<p>Hello! I recently finished coding up my first full fledged (from zero code to working app) Ruby on Rails web app. It's an app developed with a flight school in mind. The users that would sign in would be instructors that all most likely work for the same company. An instructor is able to view, edit, and delete his profile, students, lessons, and reports. The idea is pretty straightforward overall, but it required a surprisingly large amount of time to code. </p>
<p>Instead of rambling on about how to use the app, I will try to focus on what features were added, from a coder's perspective. (Also, it would be redundant to speak about the app's use since it can be found at https://github.com/Kiveo/flight-lesson-tracker and there is a demo video at : https://youtu.be/u4BGvvs3cCE ).</p>
<p>The app utilized password security, relying on the bcrypt gem and the has_secure_password method call in the model. There are validations in place for almost all attributes for each of the models: instructor, student, lesson, and report. I crafted up a couple of scope class methods to help with sorting options for the user's views. The associations were set up as:</p>

> Instructors have_many lessons<br>
> instructors have_many students, through lessons<br>
> lessons belong to instructors<br>
> lessons belong to students<br>
> students have many lessons<br>
> students have many instructors through lessons

<p>These associations and pertinent activerecord methods made the coding process easier, especially when it came time to create the lesson views. I nested the reports resource within the instructors resource, via the config routes file.</p>
<p>The controllers utilized strong params and I ended up creating a few private methods to help declutter the controller logic. This was especially true when it came time to code logic for logging in via github (Omniauth gem used ). The views and urls were set up with RESTFUL patterns in mind. The reports ended up being nested routes within instructors. Example: root/instructor/2/report/1. </p>
<p>Other than that, it was just a matter of enacting validations through the views themselves, to display appropriate messages to users if there was an error or improper input field.I created a few partials to handle forms and repeated code, in an effort to be DRY and to keep the views fairly lean.</p>
<p>I did not use the scaffold generator, and I barely used any generators beyond migration files. I think I will try my hand at using more of the rails power next project! With some css, I made it look spiffy, if somewhat silly, and that was that. Happy coding everyone!</p>

