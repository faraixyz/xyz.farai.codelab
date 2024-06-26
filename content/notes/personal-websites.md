---
title: My Personal Websites Revisited
date: 2019-02-08
latmod: 2019-02-15
tags: [my-git-revisited]
description: My personal website through the years.
draft: false
---
Over the years, I've gone through 8 personal websites. In this post, I wanna go through all the websites I had from the first one I've ever made since the summer of 2015.

## Version 1&ndash; Humble Beginnings

![the home page of my first programming blog. With a grey background, it features a round silhouette followed by the words 'Hi I'm Farai Gandiya' with links to a resume and social media paged.](/images/old-website.png)

After reading all of those personal branding articles stressing the importance of a personal website, I decided to build my first personal website in the Summer of 2015. Using what I learned from the Internet Programming class I took that May, I made this.


There isn't much to it. I used GitHub since it was (and still is) free. I also got a free domain through the [GitHub Education Pack](https://education.github.com/pack) thanks to Namecheap who I still use[^1]. Didn't know about Jekyll then, so I coded this with my bare hands. The [source code for my first personal website](https://github.com/faraixyz/farais-code-graveyard/tree/master/fgandiya.github.io-old) isn't much, but it's mine. Looking at the source code now, there are 2 TODOs

```html
<!--TODO
    1. Add Style and background
    2. Implement Responsiveness
-->
```

I didn't follow up on this since I was busy making money over the summer, but by the time I wanted to keep developing my personal website, I had moved onto making something a bit more polished.

## Version 2&ndash; Where My Site Gets Really Loud

{{% figure %}}
![The second version of my personal website, with a picture of me and some information on social links and resume against a background featuring a table with a typewriter.](/images/v2.jpg)
{{% figcaption %}}
Note that I added the image with my current gravatar since the previous one was unavailable
{{% /figcaption %}}
{{% /figure %}}

When I made this site, I had just started the [Free Code Camp Curriculum](https://freecodecamp.org). In the earlier stages, they went through using [Bootstrap](https://getbootstrap.com/) for layouts and [animate.css](https://daneden.github.io/animate.css/) for animations. For the site I'm making, using an entire library just for one animation is overkill, but I was so excited to see my face jumping up in a smooth animation. It had a couple of modals with the projects (both class assignments) I had made at the time, Missile Command and Boggle named after the original games of the same name.

It's live on [CodePen](https://codepen.io/faraixyz/full/xwdepw) since I needed it to submit projects. It was fun making this, but a lot of what I did was really unnecessary such as all the images and dependencies.

## Version 3&ndash; Not much different from Version 2

![Version 3 of my personal website](/images/new-website.png)

Still, with Free Code Camp, I decided to clean up my website a little. Instead of two giant images and an animation library, I added two solid colors and kept a picture. With a few more projects, I started to have some semblance of a portfolio.

## Version 4&ndash; Discovering Jekyll

Around this time, I started hearing a lot about this thing called [Jekyll](https://jekyllrb.com), a static site generator. Using a static site generator, you can build a template to render web pages which are supposedly faster and more secure than traditional CMS's. I'm a bit disillusioned by them now, but I'll get into that later.

Developing with Jekyll was a whole new experience. Working with the Ruby ecosystem was frustrating. It was slow and very limited. It didn't help that GitHub Pages only supported a few plugins.

## Version 5&ndash; Redesign Attempt After Redesign Attempt

![The Personal website redesign page on my CodePen account"](/images/v5.png)

My personal website has never actually been "done"&ndash; I always had something I could do better. Using CodePen, I decided to keep redesigning my website over and over again. Notice how there are two types of designs, the edgy <abbr title="I Don't Give A Fuck">IDGAF</abbr> aesthetic[^2] and the consistent header style which I got from [Cal Newport's Blog](http://calnewport.com/blog/). Funny enough, I'm using the consistent header style right now.

I don't know why I've never implemented one of these for real. Could be the stress from school. Whatever the reason, I'm using it for the time being.

You can find the redesigns on [my CodePen Collection on Personal Website Redesigns](https://codepen.io/collection/XkwWOr/#) if you wanna check them out.

## Version 6&ndash; Discovering Hugo... Before Running Back to Jekyll Again

![My Implementation of the minimal theme.](/images/v6.png)

Not sure how I found it Hugo, but once I did, I fell in love. The big thing that made me fall in love was its speed. Whereas Jekyll would build in 5 seconds, Hugo would build in less than half of a second. It was also very powerful with many built-in features that could only be fulfilled as a plugin in Jekyll.

After looking through [Hugo's Theme Collection](https://themes.gohugo.io/), I settled on the beautiful [Minimal](https://themes.gohugo.io/minimal/) by [Calin Tataru](https://calintat.github.io/). It had this minimal (pun not intended but acknowledged) look to it that I loved.

Around this time, I moved from [GitHub Pages to GitLab Pages](/content/notes/hello-gitlab-pages.md) since it supported HTTPS and had a built-in CI that supports virtually any static site generator[^3]. It was more work, but it was a better experience overall. Remember how I said that Hugo was much faster than Jekyll? Well, this was more significant in the CI since I only needed one binary rather than download the entire toolchain on each build.

If Hugo was so great then why did I move?

Well, I got frustrated with the templating and while it did a lot out of the box, it didn't support SASS without a convoluted npm build system. In a few hours, I was able to port the theme to Jekyll which restored my sanity. Sure it got a lot slower, but it was much easier to develop and write with (even though I didn't write much on my static blog).

As you'll see, this was short lived and I moved right back to Hugo.

## Version 7&ndash; Making an Actual Personal Website

![The seventh version of my personal website](/images/v7.png)

Towards graduation, I wanted to make a nice website for prospective employers to land on and learn about me. I tried to blog on two other static sites, but that never caught on (until now 🙃). I used the font [IBM Plex](https://www.ibm.com/plex/) which looked amazing despite its shitty website. I also tried to use a website gradient. Didn't really help much in attracting employers, however.

I moved back to Hugo although it wasn't really necessary since I could have just coded the webpage by hand and I'll be done.

## Version 8&ndash; Putting Everything Into One Place

{{% figure %}}
![The current website layout which is this exact post](/images/v8.png)
{{% figcaption %}}
No, this isn't an embed. I actually took a screenshot of this page as I was writing it.
{{% /figcaption %}}
{{% /figure %}}

With all the free time I've had since graduation, I decided to move everything into one place so I could figure out what to do with all the content I've made over the years. I learned a lot about Hugo, including how to add Microdata and nice RSS feeds, and I doubt I'll keep using it in the future.

## Wait, You're Going To Move Your Blog Again?

Probably. Here's where I follow up on why I'm disillusioned with static site generators. Right now, this is the 77th blog post I've ever written[^4]. It isn't like people who've been blogging for decades, but trying to move all these posts into one place is a hassle. When I try to link to older posts and reference images, I have to dig through dozens of files just to find it. I think this is why I've always used a CMS to blog like Tumblr and WordPress rather than sticking to a static site generator. [Hugo's Roadmap](https://gohugo.io/news/lets-celebrate-hugos-5th-birthday/) includes "The New York Times on Hugo" type use case. I don't doubt how powerful Hugo is[^5], but even with my inexperience in server-side programming, recreating a database in a filesystem isn't going to be fast.

I really started thinking about this after reading [Rachel Andrew's](https://rachelandrew.co.uk) opinion on [<cite>The Great Divide</cite> in front end development](https://css-tricks.com/the-great-divide/), titled [<cite>HTML, CSS and our vanishing industry entry points</cite>](https://rachelandrew.co.uk/archives/2019/01/30/html-css-and-our-vanishing-industry-entry-points/). In it, she mentions programmers' tendencies to reinvent the wheel.

> So often, we decide to solve the problems by throwing everything away. The old stuff is terrible, invented when we knew no better! We can do a far better job now, with all of our knowledge. Let’s reinvent that wheel!
>
> ...We see it with a drive to static sites, conflating speed with the lack of a database, and ending up recreating the database in the filesystem or relying on a raft of third-party services to plug the holes that would have been filled by a more traditional CMS.
>
> there are situations where the RDBMS alternative is the right choice, the static site perfect for the type of content being published. These are good solutions for particular problems. However, I’ve seen many situations where the desire to adopt the latest technology or technique leaves the project in a mess, and ultimately an expensive rebuild or refactor has to be made.
>
> &ndash;Rachel Andrews in <cite>HTML, CSS and our vanishing industry entry points</cite>

I mean, I could use [Forestry](https://forestry.io/) or [Netlify CMS](https://www.netlifycms.org/) which add content management backed by a Git backend and there are a whole lot of ways in which I could add additional functionality while keeping a static site, but it's needlessly complicated. Again, this is why I stuck with WordPress for so long. Now that I've mentioned WordPress, I could use ["headless WordPress"](https://www.smashingmagazine.com/2018/10/headless-wordpress-decoupled/), but again; it's needlessly complicated.

As Rachel said, <q>"the static site perfect for the type of content being published"</q>. So what I wanna do in the long term is have a system to author content which can be statically built to make things faster. Thing is that I'll eventually start wondering if I could only do that to certain files and how I would handle interactivity and before you know it, I've got WordPress 2.0!

One thing is for certain, I'll have to switch to a database to keep calm. 77 posts is painful to manage. I'm planning a big move to a CMS which will be done in about 2 years in time for this blog's 5th anniversary. For now, I have a couple of short term solutions.

1. Get a [frontend application for Hugo](https://gohugo.io/tools/frontends/)
2. Use some sort of Git-powered CMS.
3. Decouple the theme from the content to simplify the file structure.

[^1]: I guess that's why Namecheap added themselves to the GitHub Education Pack.
[^2]: There's this thing where accomplished programmers tend to have basic websites. I sometimes worry that I'm compensating for my lack of experience through the constant reimplementation of my personal website.
[^3]: You could still use GitHub for a Hugo powered static site. Either through an external CI server and pushing the built site to another branch or by pushing the built files.
[^4]: Excluding the posts, I couldn't find nor could be arsed to move over.
[^5]: Technically I do doubt it. Why else would this section be here?
