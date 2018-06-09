---
layout: post
title:      "A CLI App And The Woes Of Scraping"
date:       2018-06-09 20:39:57 +0000
permalink:  a_cli_app_and_the_woes_of_scraping
---


  I made a CLI called FlyQuick. It needs some refactoring, but overall I am pretty proud to have finally created something from the ether. It began as my idea, one from long ago. I've been a pilot for about 18 years, as of 2018. From flying small trainers to small business jets, I've always been irked by how cumbersome the navigation radios are in aviation. Even the latest and greatest touchscreen technology still requires finesse when trying to enter " K T P A" using a twist knob with even a small amount of turbulence. 
  Years later, I get into coding and decide to begin the initial idea. I start coding FlyQuick. To keep it simple, a user basically selects a US state and then an airport from generated lists. Thereafter, the user is presented with a consolidated list of information a general aviation pilot would want, without having to browse charts or an in-flight gps. 
	As a simple project, it scrapes data from an aviation database, using the Ruby friendly Nokogiri. When first learning about Nokogiri, it became apparent that CSS selectors would help tremendously with the scraping problem. So, I happily required Nokogiri in my project tree. Then I took a closer look at the html of the webpage. Tables. Tables everywhere!
	For many of the pages, ALL of the information and layout...pretty much everything was tables. It felt like looking at a webpage from the 1990's. Several pages, upon inspection, had zero css selectors. No classes. No ID's. Just pure html tables. What a nightmare!
	It quickly became apparent that if I was going to use the website and database I had settled on for my project, I was going to have to get very comfortable with nth child searching. That was quite a hurdle for a fledgling coder. I ended up doing many pry (binding.pry - from 'pry' ruby gem). There were probably quicker ways to do it, but as a novice coder, I used the tools and knowledge available.
  Ultimately, I settled on using much less than optimal DRY coding. Example: 
	  
		tables = doc.search('table')
		airport_table = tables[4]
		airport.name_variable = airport_table.search('a')[1].text
		
  Not very DRY at all. Could I at least put it all together, something like:
    
		airport.name_variable = doc.search('table')[4].search('a')[1].text

  Sure, something similar probably. Perhaps I could have also used some nth child type locating as well. The problems I came across when considering that were as follows. For starters, I wasn't very comfortable with the vast knowledgebase and tricks surrounding Nokogiri. I am sure there were myriad ways to simplify the same execution. Another concern, once I nixed using nth child stuff, was the debate between DRY code and readable code. Especially of concern was code I could look back on and understand clearly and quickly what I had done. Similar to how coders like to segment responsibility to separate classes, I liked the idea of having named variables, explaining the 'digging' process.
  As above, it is clear that I wanted the tables. Then, it is clear I had narrowed down the tables to a single airport specific table (Reminder: the entire page, from ad banners to footers and headers, was all tables and little to no CSS). After getting the table concerning the content I wanted scraped, I then wanted to give my airport object the variable 'name'. Again, I am painfully aware there were better ways to do it. This way just made sense to me and got my program running. I also felt I could see this code later on and pretty quickly surmise the thought process. That was a large devision maker. 
	I hope to look back on this project sometime and refactor it in many ways, but mainly I want to get more comfortable with selecting elements from the DOM. It is clear that the basics of web apps really do boil down to knowing the core language of the web: HTML. 
	Food for thought: would it be better to separate the scraping class from the airport class? I'm thinking most likely, especially if I want to expand the app in the future. For now, it shall suffice. Please forgive me, future self! 
	
	Final note: Next time, I might just choose a source that allows for scraping like this:
	  airport.name_scrape = doc.search('a.name') 
		
		...but where's the fun in not learning the hard way?
