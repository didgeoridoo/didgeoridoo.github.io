---
layout: post
title:  "Thoughts on blogging with Jekyll"
featured-image: "microphone.jpg"
featured-alt: "A microphone set up on a stage"
# featured image art direction (default is 0% 50%)
featured-offset-top: "50%"
featured-offset-left: "50%"
subtitle: "Or: this is going to get old really fast"
date:   2014-02-18 18:31:00
categories: complaints
---

Twenty-four blissful hours ago, I built and launched a new webpage using Jekyll, hosted on [Github Pages](http://pages.github.com). You may be familiar with it; it's the one you're currently reading. DNS propagation issues aside, I was excited about the launch.

"Perhaps", I thought, "I will write more if I have a nice-looking, personal place to do it! The publishing process seems easy. You just... something... Markdown... and... git push? Whatever, I'll figure it out."

Ah, the innocence of youth.

If you're not familiar with the process for blogging on Github Pages with Jekyll, here is a quick summary:
-Think of blogging with WordPress.
-Now think of the EXACT OPPOSITE THING.

To be fair, I have an odd set of personal needs that might not be a good fit with the platform. For example, I do not always know what date it is. This can be slightly inconvenient, because that's the first thing you have to manually enter as the file name for your post (Jekyll is unbending on this point). In the YAML front matter of the post (i.e. required metadata), you again must enter the date, plus the time in 24-hour format, which seems to me suspiciously European.

So, what happens when a UX guy runs into a process that is, for lack of a better word, poo?

REDESIGN!

Question: You're not going to try to design and implement a mini-CMS to integrate with GitHub Pages are you? Because that would be a terrible idea and a tremendous waste of time.
Answer: FUCK YES I AM
Question: Might I suggest just trying a more user-friendly blogging platform, and leave Github Pages to proper software developers?
Answer: NO I AM GONNA MAKE THIS THING MY BITCH

So, let's take a look at how you publish a new post. Searching for "Jekyll blogging workflow" on Google led me to a fellow named Raj Rathore. Raj is quite happy with his workflow, calling it ["perfect"](http://qubitlogs.com/Workflow/2013/01/22/jekyll-blogging-reference-and-perfect-workflow-guide/#.UwPnMEJdU0o). It involves a lot of command-line mucking around, but it boils down to:
-Create a new .markdown file
-Add YAML front matter
-Write your post
-Deploy it to your server

In Raj's world, traffic jams are made of ice cream trucks driven by puppies.

In practice, I've found that the "real" workflow is actually:
-Log onto GitHub and clone the repo, or navigate to my local repo on the command line and "git pull" the latest version.
-Navigate to the _posts folder and copy the most recent post so I don't have to remember how to format the YAML front matter.
-Find out what fucking date it is so I can create a new file (yes, this is actually a problem for me).
-Convert the time in my head to 24-hour time (this is less of a problem for me but come on)
-Write my post
-Find a featured image that somehow captures my meaning, or doesn't.
-Copy the image into my /images directory in my local repo
-"git push" back to GitHub

This feels a lot more like engineering than writing.

What if you could use the GitHub [contents API](http://developer.github.com/v3/repos/contents/) to perform simple CRUD commands on your own repo, from the comfort of not-the-command-line? You could easily save templates, upload and compress images, and even know what date it is. I imagine a workflow like:
-Login to the application using your GitHub credentials
-Create a new post, with automatically-generated file name and YAML front matter
-Preview the rendered Markdown using your actual CSS, so it's not a mystery what it ultimately will look like
-Upload images that can be smartly compressed before getting dropped into your repo

So, any thoughts on this approach? Anyone want to try to stop me? Because, please stop me. Otherwise I actually might do this.