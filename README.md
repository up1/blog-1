# [Stack Exchange Blog](http://blog.stackexchange.com/)

## Getting Started
This blog runs on [Jekyll](http://jekyllrb.com/) and [GitHub Pages](https://pages.github.com/). Posts are written in [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

If you are actively involved in improving the infrastructure of this project, you should read the documentation for these platforms thoroughly (they're pretty short as it is). If you are simply contributing, this guide should be enough to get you going.

## Quick Links
 - [Add yourself as a contributor on the blog](https://github.com/StackExchange/blog/new/master/_authors) ([See an example file](https://github.com/StackExchange/blog/edit/master/_authors/jonhmchan.md))
 - [Publish a new post](https://github.com/StackExchange/blog/new/master/_posts) ([See an example file](https://github.com/StackExchange/blog/edit/master/_posts/2014-1-28-My-First-Six-Weeks-Working-At-Stack-Overflow.md), [published version](http://stackexchange.github.io/blog/01/28/My-First-Six-Weeks-Working-At-Stack-Overflow/))
 - [Dev blog (for employees only, where to preview posts before going live)](http://dev.blog.stackexchange.com/)
 - [Internal image uploader (for employees only, must be on VPN or on office network)](http://blogtools.ds.stackexchange.com/)
 - [Company editorial board and calendar (post ideas and see schedule)](https://trello.com/b/WYAPaUEC/blog-editorial-and-calendar)

## What is this blog for?
This is the official company blog for Stack Exchange. Everything related to new features, announcements, engineering projects, and all things Stack Exchange live on this blog. The contributors on this blog are Stack Exchange employees, but in the future, we may open this up to outside contributors as well.

### I have an idea for / want to write a post, what should I do?
1. Go to our [Blog Editorial and Calendar Trello board](https://trello.com/b/WYAPaUEC/blog-editorial-and-calendar) and add any and all of your ideas to the `Ideas/Backlog` column.
2. In the card, you need to do the following (see [example here](https://trello.com/c/CtdGiI8C/5-how-we-built-our-brand-new-blog)):
 - Add yourself as a member and anyone else you think might be helpful in writing the post
 - Designate a single **author** in the description that is going to be responsible for writing the post
 - You should also put a **description** of what the post is going to be about
 - Add any relevant **tags** like `announcement`, `diversity`, or `engineering` onto the card
3. As cards get added, Rachel Maleady and Jon Chan will go through all the cards in the `Ideas/Backlog` column, and move anything we want to discuss into the `Being Scheduled This Week` column. Sometimes things that *have* to get scheduled (like the regular podcast posts) will get added directly into this column. If your card got moved into the `Being Scheduled This Week` column, feel free to join Rachel and Jon in the meeting to chat about your ideas.
4. Every week during the editorial meeting, Rachel and Jon will move cards from `Being Scheduled This Week` into a `Publishing This Month` or `Publishing Next Month` column. Once that's done, you should start [writing your post](https://github.com/StackExchange/blog#2-publishing-a-post) and we're going to ocassionally heckle you about it until it's published :) If you have trouble figuring out how to do this, feel free to ask Jon or Rachel.
5. As you write your post, feel free to commit it. Jon and Rachel will constantly be looking at what gets added here and nothing will get published publicly until we manually hit the production build, so don't worry too much about making mistakes and stuff. As you write and make commits, it automatically builds on an internal dev tier at http://dev.blog.stackexchange.com/, so if you want to see what it looks like before you publish, you can see it there.
6. Once the deadline arrives, we'll check with you to make sure it's exactly as you like it, then we'll push to production!

## Quickstart

###1. Add yourself as a contributor with an author file

[Add yourself as a contributor on the blog](https://github.com/StackExchange/blog/new/master/_authors) ([See example file](https://github.com/StackExchange/blog/edit/master/_authors/jonhmchan.md))

You need to create a new markdown file with your username in the `_authors` folder to be included as a contributor on the blog. For example, Jon Chan uses the username `jonhmchan` so he would create a new file named `jonhmchan.md`. In the content of this markdown file should be the following (you don't need the square brackets):
```
---
layout: author
id: [username, must be same as file name]
name: [your full name]
job: [job title]
avatar: [url to an image to be used with all your posts. Most people use their Gravatar pic url]
twitter: [your twitter handle, without the @]
website: [url to your personal site, optional. You can remove this entire line if you don't have one.]
---
```
So Jon Chan's `jonhmchan.md` file would look like:
```
---
layout: author
id: jonhmchan
name: Jon Chan
job: Developer, Head of Evangelism
avatar: https://www.gravatar.com/avatar/0090f1f22a03e38ca61dc955e1d0a346?s=100
twitter: jonhmchan
website: http://www.jonhmchan.com/
---
```
**How to add this file**

If you are a developer, you can do this simply by submitting a PR or adding this file to the `_authors` directory. If you are not a developer, you can use [this link on GitHub](https://github.com/StackExchange/blog/new/master/_authors) to create this file, then submit your changes by adding a commit message like `Added [your name] to authors` and hitting the `Commit new file` button:

![Adding yourself as an author](images/adding_authors.png)

Once you do commit this file, you may be asked to create a pull request. Click `Create Pull Request` to do so:

![Creating a pull request](https://help.github.com/assets/images/help/pull_requests/pull-request-click-to-create.png)

Then on the next screen, you can submit the pull request:

![Submitting a pull request](https://help.github.com/assets/images/help/pull_requests/pullrequest-send.png)

###2. Publishing a post

[Publish a new post](https://github.com/StackExchange/blog/new/master/_posts) ([See example post file](https://github.com/StackExchange/blog/edit/master/_posts/2014-1-28-My-First-Six-Weeks-Working-At-Stack-Overflow.md), [published version](http://stackexchange.github.io/blog/01/28/My-First-Six-Weeks-Working-At-Stack-Overflow/))

To create a new post, you need to create a new markdown file with a particular format in the `_posts` folder in order to publish. The file needs to include the date and title seperated by dashes: `YYYY-MM-DD-Title-With-Dashes-As-Spaces.md`. For example, Jon Chan published a post on January 28th, 2014 titled "My First Six Weeks Working at Stack Overflow". So the title of his file was `2014-1-28-My-First-Six-Weeks-At-Stack-Overflow.md`.  In the content of this markdown file should be the following (you don't need the square brackets): 
```
---
layout: post
title: [title of your post]
author: [your author id]
date: [the date you want this to be published in YYYY-MM-DD HH:MM:SS format. If in the future, will be put in draft mode and will publish at that time. Optional, you can remove this whole line]
draft: [true or false, will hide the post from any display lists. If not a draft, you can also remove this whole line]
hero: [url of a high quality hero image to be used for your post. Optional, you can remove this whole line]
source: [url of the original post so a source banner will be added to the post. Optional, you can remove this whole line]
description: [a description that will show up in search results, up to 160 characters. Optional, you can remove this whole line]
tags: [what channel this post belongs to (engineering/company), and any related tags, required]
---
[Content of your post in markdown]
```
So Jon Chan's post `2014-1-28-My-First-Six-Weeks-At-Stack-Overflow.md` would look something like the following:
```
---
layout: post
title: My First Six Weeks Working at Stack Overflow
date: 2014-01-28
author: jonhmchan
hero: https://ununsplash.imgix.net/photo-1416339306562-f3d12fefd36f?q=75&fm=jpg&s=dd8bffcffb3d622bea05c74d203121c6https://unsplash.imgix.net/photo-1416339442236-8ceb164046f8?q=75&fm=jpg&s=8eb83df8a744544977722717b1ea4d09
source: http://www.jonhmchan.com/blog/2014/1/16/my-first-six-weeks-working-at-stack-overflow
tags:
 - engineering
 - onboarding
---

I started working at [Stack Exchange](http://www.stackexchange.com/) (which many know for/as [Stack Overflow](http://stackoverflow.com/)) as a software developer just six weeks ago. This (lengthy) post is about a number of things: what it was like relearning a lot of what I know about web development, the challenges and resources I encountered doing so, and a few pointers others might benefit from on-boarding on a new development team.

...
```
You can see what [this post](http://stackexchange.github.io/blog/01/28My-First-Six-Weeks-Working-At-Stack-Overflow/) looks like as a full markdown file by going to [this link](https://github.com/StackExchange/blog/edit/master/_posts/2014-1-28-My-First-Six-Weeks-Working-At-Stack-Overflow.md).

**How to add this file**

Adding this file is very similar to adding your original authors markdown file. You can use git to add your post markdown file in the `_posts` folder, or you can use the [GitHub user interface](https://github.com/StackExchange/blog/new/master/_posts) to do so. Note that the moment you commit this file, it will be published to the blog.

**Writing your post with Markdown**

Everything following the second set of three dashes in your post markdown file will be the content of your post. We use [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) to format the post.

**Uploading Images**

Adding images to your post requires you to upload the image and use the URL in your markdown. We have an internal image uploader tool that you can access at the following link: http://blogtools.ds.stackexchange.com/ . You will need to be connected to the VPN or wired to the internal office network.

In addition to the different methods, there are some basic guidelines to what is allowed:

 - Your images should *never* be bigger than 50KB
 - Maximum width of any image should be 800 pixels
 - Do your best to avoid images with text in them, it makes it difficult to use as a background

 Note that using our internal tool will host the images in the right place and also deal with resizing/compressing.

**Drafts**

You can always set your posts as drafts. You can do this by adding the line `draft: true` into the metadata of your post. Putting your post into draft mode means it won't show up anywhere that blog posts are listed, but you can still see the post at its individual URL.

**Adding tags**

Every post is required to have at least one tag: either `company` or `engineering` depending on which channel it belongs on (it can also have both). You can then add any additional tags afterwards.

Jekyll has some support for tags, but requires that you do a little bit of work in order to make sure new tags are accommodated. All tags must have a markdown file named after the tag in the `_tags` folder. For example, the `onboarding` tag markdown file `onboarding.md` looks like this:
```
---
layout: tag
slug: onboarding
---
```
When writing a new post, you can add space separated tags at the top of the post markdown file. 
```
---
layout: post
title: [title of post]
author: [author id]
tags:
- [tag1]
- [tag2]
- [tag3]
---

```
Any tags that already have an associated markdown file in the `_tags` folder will get its own page at `/tags/[tag-name]` and will be featured on the homepage. However, if you are adding a new tag, make sure that you create the appropriate markdown file in the `_tags` folder.

**Where to get good hero images**
 - [Unsplash](https://unsplash.com/grid)
 - You can also upload them to `images` and it will be accessible using `/images/path-to-your-image`
 - Search our internal drive for "Photos" there are a number of professional photos we have in store

**Code snippets**

Jekyll has support for code snippets and highlighting built-in using [Pygments](http://pygments.org/). To include a codeblock with in your markdown, use the following syntax:
```
{% highlight [language] %}
[Your code here]
{% endhighlight %}
```
So if you were going to be including a snippet of Ruby code in your post, it would look like:
```
{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}
```

## Making code changes

If you are interested in making changes to the design, functionality, or structure of the blog, you're going to need to set up a local environment and understand some of the technologies behind the site.

**1. Install Jekyll and dependencies.** First thing you're going to need to do is set up Jekyll and the appropriate dependencies so you can develop locally. The easiest way to install everything is to use [RubyGems](https://rubygems.org/pages/download) and follow the instructions on the [Jekyll](http://jekyllrb.com/docs/installation/) website. In addition to the basic Jekyll installation, you also need to install a few dependency gems. After install RubyGems on your machine, you really only to run two basic commands:
```
gem install jekyll
gem install jekyll-sitemap
gem install jekyll-redirect-from
gem install rouge
```

**2. Run a local version of the blog.** Using Git, clone the latest version of this repository to your local machine using the following command:
```
git clone https://github.com/StackExchange/blog.git
```
Then go into root of the folder and run `jekyll serve`:
```
cd blog
jekyll serve
```
This will get a local version of the blog running on your machine, accessible on `localhost:4000/blog/`

**3. Read up on the documentation.** To really understand how to develop the site there are a few things you're going to need to read up on to make meaningful changes:
 - [Jekyll](http://jekyllrb.com/docs/home/) The static site generator used for the site
 - [GitHub Pages](https://help.github.com/articles/using-jekyll-with-pages/) How the site is hosted
 - [Liquid](https://docs.shopify.com/themes/liquid-documentation/basics) The templating language used with Jekyll by Shopify
 - [Stack Overflow Careers Pattern Library](http://stackexchange.github.io/uikit/index.html) Our pattern library by our designers that includes a full LESS framework for rapid development
