---
layout: post
title: "Demystify the Flatiron Blog"
date:       2018-11-20 18:30:00 +0000
permalink:  demystifying_the_flatiron_blog
---
 
The code school I graduated from, Flatiron, had blogs pre-generated for students. Maybe you have a similar circumstance. Either way, if your scenario involves GitHub pages, Jekyll, and a blog: this is for you. 

I had absolutely ZERO idea how the blog at Flatiron worked. None. I pressed "make a post", filled in a WYSIWYG editor, and *poof*! Magic. Some students probably looked into this stuff way before I did, but it was not until I was graduated that I even thought to try and really personalize the blog. Ultimately, I entirely took it over and am all the happier about it. Honestly, I hated the standard layout and nothing screams "novice" more than a blog that *literally* looks like hundreds of others. 
	
*Disclaimer: I opted for the personal domain option the school offered. I do not know if this guide will apply as neatly for students who did not claim their own domains. That said, I suspect the information will be applicable to both scenarios*
	
Let's talk about some of the technology involved. The basic lowdown is as follows:  
1. The blog is driven by a framework known as Jekyll. Jekyll is responsible for static site generation (aka: your blog's generation).  
2. The page is hosted on GitHub pages as a *username.github.io* repo of your GitHub account.  
3. After a post is created, the static site generator causes a re-rendering of your GitHub pages website, thus the delay period many experience between posting and seeing their blog.  
4. The file structure(content) associated with your blog is, of course, hosted on GitHub. It's worth mentioning that the posts themselves are saved as Markdown files. Markdown basically converts plain text into HTML. 

There are other technologies involved, but they are not pertinent to what we will be doing. In an effort to keep this blog from being a novel or split into several posts: I am going to be glossing over several things. Feel free to contact me for corrections or questions. Moving on...

Ready to take control of your blog, students? Good. Let's do this! I am a fan of lists, btw.  
1. Login to your GitHub account and find the repository named: *username.github.io* [username is meant to be whatever your GitHub account name is].
2. Take a glance at the code folder structure. Find the folder named _posts. Look inside. Those are markdown files. They're your posts.  
*Example: 2018-11-20-blog-title-that-seems-familiar.markdown*
3. (Option A): **Using the naming convention**, create a new .markdown file and write up a post. Even without knowing Markdown (or html, arguably), you should be able to whip together a post. Save it.   
    (Option B): Clone the repo to your local environment and use those git skills you've been polishing to create-commit-push yourself a new post (*date-named_post.markdown file*). *I prefer this method*.  

The image below shows a github warning email for when we don't follow naming conventions.
![GitHub failure message example](./img/github-warning.png "GitHub warns about naming scheme")

__Pro-tip__: If you do not want to bother messing with anything but the WYSIWYG editor of flatiron, then at least know that you can put html tags inline, alongside your text. Even better, use markdown styling (included in the sources below)! If you have a solid brick wall of words that span the entire page, with no breaks or white space... then you're approaching this whole developer/coder thing wrong. It's fine starting out, but now that you've read this: keep growing!

Here is where I leave you guys an assignment. Alter your CSS files/code. You guys choose how you want to do this. I can't give you all the answers, can I?  
I will give you a tip: the css files are within the css folder of your Jekyll file structure. It should be on the same 'level' as the _posts. If you're not comfortable with bootstrap, LESS, pre-processing/compiling/minimizing, that's OK. You could still just use the normal css files, but CAUTION: I do not recommend doing that. It can make later learning/using LESS a little awkward in the file structure. My recommendation for those who don't want to dive deep into pre-processors, compiling, and min files just yet: leave the css for now. In the meantime, reference my source links to learn more. Or, of course, you could use <span style="color: green">inline css</span>.

At this point, the guide is pretty much done. You should now know what tech powers your blog, where to access the source-code, and it's up to you what method you choose to continue posting. Maybe you want to keep the original setup. Maybe you enjoy posting from the school platform. Or, maybe you decide to take a shot at using Jekyll, Less, markdown, and other such spiffy things! Regardless, knowledge is power and you have options now.

I hope this was helpful. If you guys have any questions, comments, or suggestions: feel free to reach out. Have a happy holiday season, enjoy some coffee, and code on! 

*SOURCES:*  
*[GitHub Guide](https://guides.github.com/introduction/git-handbook/)*   
*[Markdown](https://daringfireball.net/projects/markdown/)*  
*[Basic Markdown Tutorial](https://gist.github.com/budparr/9257428)*

*[Jekyll Webpage](https://Jekyllrb.com/)*  
*[Github Pages](https://pages.github.com/): advert/explanation:* (first 2 minutes is a good overview)  
*[LESS CSS](http://lesscss.org/)*  

*[Bootstrap 3](https://getbootstrap.com/docs/3.3/)*  
*[Bootstrap 4](http://getbootstrap.com/)*  

*[Learn.co/Flatiron Blog FAQ](http://help.learn.co/?q=blog)*

*Notes:*  
*(11/21/18): There are different kinds and uses of the mentioned technologies, but for the purpose of this post, I've simplified things. I encourage everyone to further research all things code. See my sources above for the aforementioned tech stuff.*