---
layout: post
title: "Demystify the FlatIron Blog"
date:       2018-11-20 18:30:00 +0000
permalink:  demystifying_the_flatiron_blog
---
 
The code school I graduated from, Flatiron, had blogs pre-generated for students. Maybe you have a similar circumstance. Either way, if your scenario involves github pages, jekyll, and a blog: this is for you. 

I had absolutely ZERO idea how the blog at FlatIron worked. None. I pressed "make a post", filled in a WYSIWYG editor, and *poof*! Magic. Some students probably looked into this stuff way before I did, but it was not until I was graduated that I even thought to try and really personalize the blog. Ultimately, I entirely took it over and am all the happier about it. Honestly, I hated the standard layout and nothing screams "novice" more than a blog that *literally* looks like hundreds of others. 
	
*Disclaimer: I opted for the personal domain option the school offered. I do not know if this guide will apply as neatly for students who did not claim their own domains. That said, I suspect the information will be applicable to both scenarios*
	
Let's talk about some of the technology involved. The basic lowdown is as follows:  
1. The blog is driven by a framework known as Jekyll. Jekyll is responsible for static site generation (aka: your blog's generation).  
2. The page is hosted on github pages as a *username.github.io* repo of your github account.  
3. After a post is created, the static site generator causes a re-rendering of your github pages website, thus the delay period many experience between posting and seeing their blog.  
4. The file structure(content) associated with your blog is, of course, hosted on github. It's worth mentioning that the posts themselves are saved as Markdown files. Markdown basically converts plain text into HTML. 

There are other technologies involved, but they are not pertinent to what we will be doing. In an effort to keep this blog from being a novel or split into several posts: I am going to be glossing over several things. Feel free to contact me for corrections or questions. Moving on...

Ready to take control of your blog, students? Good. Let's do this! I am a fan of lists, btw.
1. Login to your github account and find the directory named: *username.github.io* [username is meant to be whatever your github account name is].
2. Open the code and take a glance at the folder structure. Find the folder named _posts. Look inside. Those *2018-11-20-blog-title-that-seems-familiar.markdown* files are markdown files.   
	

__Pro-tip__: If you do not want to bother messing with anything but the WYSIWYG editor of flatiron, then at least know that you can put html tags inline, alongside your text. Even better, use markdown styling (included in the sources below)! If you have a solid brick wall of words that span the entire page, with no breaks or formatting, then you're approaching this whole developer/coder thing wrong. Sorry, not sorry.

I hope this was helpful, enlightening, entertaining, or at least infuriating. Enjoy some coffee, have a happy holiday season, and code on! 

*sources:*  
*[Markdown](https://daringfireball.net/projects/markdown/)*  
*[Basic Markdown Tutorial](https://gist.github.com/budparr/9257428)*

*[Jekyll Webpage](https://jekyllrb.com/)*

*[Github Pages](https://pages.github.com/): advert/explanation:* (first 2 minutes is a good overview)
<iframe width="1280" height="720" src="https://www.youtube.com/embed/2MsN8gpT6jY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>