---
layout: post
title:      "Rake, Rakefile, Tasks, and Pry Console"
date:       2018-07-01 22:36:57 +0000
permalink:  rake_rakefile_tasks_and_pry_console
---


If, like me, you've seen tutorial videos about beginner ruby coding, then you've come across this issue:
"Ok, great, now let's test this out. I'm just going to open my console...and magic magic magic, GREAT it works!".
Wait. What the heck is all that magic?

How did :tutor_person just open a console inside his command prompt?! How is he running pry without dropping a binding somewhere? What is this voodoo? 

I am sure I am not alone in having decided to let that knowledge skip me and I focused on learning the task at hand. Well, I finally climbed my way out of the ignorance hole, just enough, to learn about tasks. 
> The magic has a name, it turns out it is called 'Rake'.
Ok, let's break this down into parts:
1. What is Rake?
2. What is a rakefile?
3. What is a task?
4. How do I access the console without dropping a Binding.pry (This is the question I wanted to know so badly).

A quick note: I am only just learning about Rake, rakefiles, tasks, and calling them. Here are a couple sources if you'd like to know more: [The Rake Github Page](https://github.com/ruby/rake) OR [Someone's Ruby Rake Tutorial](https://lukaszwrobel.pl/blog/rake-tutorial/)

*What is Rake? What is a rakefile? What is a task?*
Rake is a task management and automation tool. It was created by Jim Weirich, a notable rubyist. Rake allows users to create tasks, which can describe dependencies or simply 'do something' the user wants. There are default tasks available as well. Rake is written with ruby syntax and the 'tasks' it utilizes are stored in a 'Rakefile'. It is a more robust than I have described, including namespacing and creating dependency interactions, but a simple overview for now is sufficient.

*How do I access the console without dropping a Binding.pry?*
Ok, the fun part! As I was learning to create a basic Rake task, I accidentally stumbled across the magic I had seen in ruby tutorial videos[to clarify: videos unrelated to Rake itself]. Bear with me just a tiny bit longer. Let's dive into a basic task.

```
#Inside a Rakefile

task :salutations
  puts "Hello World!"
end 
```
Presuming this rakefile is somewhere in our project tree, we can use our command line to type in 'task salutations' and it should basically spit out our 'Hello World!'. Ok, that's fairly neat, but nothing regular ruby methods aren't already doing for us. The power really comes in when using Rake beyond simple puts, obviously. Still, it gives the reader an idea of what they're looking at when opening a Rakefile. The example provides a basic understanding of the syntax and does some demystifying for us.
Let's now take a look at an example concerning the console and 'Pry':

```
task :console => :environment do
  Pry.start
end

task :environment do
  require_relative 'config/environment'
end
```

There is a sequence dependency setup here, but more importantly: the task ":console" has been created. Now, when we are in our directory, we can call `rake console`. This will drop us into the wonderful world of Pry!
```
[12:34:45] (master) learning-magic-v-0
//  rake console
[1] pry(main)> _
```

This little article doesn't do justice to Pry, Rake, or Ruby. It does, hopefully, provide a fairly short answer and explanation to, "What is that magic?" syndrome. Learners may be wondering about this when watching videos where an instructor seemingly drops into a console magically from a command prompt. I certainly used to wonder about it a lot! 

Here are a couple more useful links:

[Pry](http://pryrepl.org/)

[Ruby Documentation](https://www.ruby-lang.org/en/)



