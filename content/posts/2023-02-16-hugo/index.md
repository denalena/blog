---
title: "Using Hugo and GitHub Pages to blog"
date: 2023-02-16 07:09:00
---

When I started this blog, I wanted to make a post of how I set it up. Now comes is the time! Although I have to say, I kind of forgot what my pain points were back then, but I remember that I tried using GitHub Pages and Jekyll, and with both of them I wasn't happy.

What I wanted was:
- publishing by git
- posts as markdown
- a simple way to preview posts before publishing

My solution now is using [Hugo](https://gohugo.io/), another popular static site generator written in go. I really like the setup because it's quite simple to get started. Basically the steps are:

- [Install Hugo](https://gohugo.io/installation/) and [create a site](https://gohugo.io/getting-started/quick-start/)
- This creates a directory containing all the files; create a git repo and push it to GitHub
- Set GitHub Actions as the source for GitHub Pages in the repo settings
- Add the Hugo workflow by GitHub Actions

And you're done! Now you can use `hugo` to build the site, and if you commit and push the changes, the site gets updated. Also, `hugo server` can be used to easily serve the content locally to get a feel for it. 

Note that your repo has to be public if you don't want to pay for using GitHub Pages. I still have to figure out some configuration and a nice theme, but this is a nice way to go forward.

By the way, I noticed that it's way easier for me to just sit down and write/draft blog posts in the note taking tool of my choice (which is currently [Joplin](https://joplinapp.org/)) instead of worrying about how the blog works.
