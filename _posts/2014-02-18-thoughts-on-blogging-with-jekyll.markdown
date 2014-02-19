---
layout: post
title: Thoughts on blogging with Jekyll
"featured-image": microphone.jpg
"featured-alt": A microphone set up on a stage
"featured-offset-top": "50%"
"featured-offset-left": "50%"
subtitle: "Or: this is going to get old really fast"
date: {}
categories: complaints
published: true
---

Twenty-four blissful hours ago, I built and launched a new webpage. You may be familiar with it; it's the one you're currently reading. It's my first foray into blogging using Jekyll, hosting through [Github Pages](http://pages.github.com). DNS propagation issues aside, I was excited about the launch. 

"Perhaps", I thought, "I will write more if I have a nice-looking, personal place to do it! The publishing process seems easy. You just... something... Markdown... and... git push? Whatever, I'll figure it out."

Ah, the innocence of youth.

If you're not familiar with the process for blogging on Github Pages with Jekyll, here is a quick summary:

1. Think of blogging with WordPress.
2. Now think of the EXACT OPPOSITE THING.

To be fair, I have an odd set of personal needs that might not be a good fit with the platform. For example, I do not always know what date it is. This can be slightly inconvenient, because that's the first thing you have to manually enter as the file name for your post (Jekyll is unbending on this point).

In the YAML front matter of the post (i.e. required metadata), you *again* must enter the date, plus the time in 24-hour format, which seems to me suspiciously European.

So, what happens when a UX guy runs into a process that is, for lack of a better word, poo?

### REDESIGN!

*Question:* You're not going to try to design and implement a mini-CMS to integrate with GitHub Pages are you? Because that would be a terrible idea and a tremendous waste of time.

*Answer:* FUCK YES I AM

*Question:* Might I suggest just trying a more user-friendly blogging platform, and leave Github Pages to proper software developers?

*Answer:* NO I AM GONNA MAKE THIS THING MY BITCH

So, let's take a look at how you publish a new post. Searching for "Jekyll blogging workflow" on Google led me to a fellow named Raj Rathore. Raj is quite happy with his workflow, calling it ["perfect"](http://qubitlogs.com/Workflow/2013/01/22/jekyll-blogging-reference-and-perfect-workflow-guide/#.UwPnMEJdU0o). It involves a lot of command-line mucking around, but it boils down to:

1. Create a new .markdown file
2. Add YAML front matter
3. Write your post
4. Deploy it to your server

In Raj's world, traffic jams are made of ice cream trucks driven by puppies.

In practice, I've found that the "real" workflow is actually:

1. Log onto GitHub and clone the repo, or navigate to my local repo on the command line and "git pull" the latest version.
2. Navigate to the _posts folder and copy the most recent post so I don't have to remember how to format the YAML front matter.
3. Find out what fucking date it is so I can create a new file (yes, this is actually a problem for me).
4. Convert the time in my head to 24-hour time (this is less of a problem for me but come on)
5. Write my post
6. Find a featured image that somehow captures my meaning, or doesn't.
7. Copy the image into my /images directory in my local repo
8. "git push" back to GitHub

This feels a lot more like engineering than writing.

What if you could use the GitHub [contents API](http://developer.github.com/v3/repos/contents/) to perform simple CRUD commands on your own repo, from the comfort of not-the-command-line? You could easily save templates, upload and compress images, and even know what date it is. I imagine a workflow like:

1. Login to the application using your GitHub credentials
2. Create a new post, with automatically-generated file name and YAML front matter
3. Preview the rendered Markdown using your actual CSS, so it's not a mystery what it ultimately will look like
4. Upload images that can be smartly compressed before getting dropped into your repo

So, any thoughts on this approach? Anyone want to try to stop me? Because, [please stop me](http://www.kayt.es/contact). Otherwise I actually might do this.

### Edit

I seem to have independently invented [prose.io](http://prose.io). I'm adding this edit from their delightful web interface. Review to come.

### Edit the second

My first pass at Prose.io resulted in a "build failed" error when I tried to update this post with the previous edit (meta!). From what I can find in a brief search online, this may have something to do with GitHub Pages' implementation of Jekyll. More to come.
