---
title: What I Did At My Job In The College Library
description: What I did during my time working as a technology consultant at the college library.
series: [my-git-revisited]
date: 2019-02-09
lastmod: 2019-10-28
draft: false
---

In college, I worked at my college's library (Vogel) for their technology consulting team ELITE. After two years of trying, I was happy to have finally gotten the job. Not just any job, a job that was relevant to my future career. Better yet, I could finally sit down instead of running around and prepping food[^1]. While I've talked about this on the home page under the section Education & Work Experience, I want to go into more detail. Oh, throughout the post, whenever you see Todd, that was my boss.

## Web Development

As the CS major with a little web development experience, I was responsible for maintaining the website. Most of my work was done using version control that was nothing more than sending emails to Todd with file names like:

* `hours-script.js`
* `hours-script-2.js`
* `hours-script-3.js`
* `hours-script-final.js`
* `hours-script-final-final-2.js`

Not elegant, but it worked.

### Hours Script

![An illustration of the hours script.](/images/hours-demo.png)

The first thing I did for the website made a script that would display the library's hours. It wasn't perfect, but it worked. Looking at [the code for the hours script](https://library.wartburg.edu/scripts/hours1.js), the first thing I see is this

```js
//Not Completed
//I Overlooked Something
/*
* Test this
* Out more Comments
*/
```

Even though it's "not completed" since "I overlooked something", it still does it's job three years later. Here's how the script worked. It would

1. Check the current day
2. If the day is a holiday, display a message saying it's closed.
3. If there are special hours (due to Ash Wednesday, the day before Thanksgiving), show the special hours
4. Otherwise, show the default hours

While it still works, it's "not completed". Ideally, I would have made. That way my supervisors wouldn't have to modify the code every time something happened(see the code below for reference).

```js
//enter holidays like 02/26 as 0226
var holidays = ["011", "015", "016", "033", "034", "0310", "0331",                 "041", "0414", "0421", "0422", "0428", "0429",                     "0526", "0527", "0528", "074", "0826","1122",                      "1123","1124", "1215", "1216", "1222", "1223",                     "1224", "1225", "1226", "1227", "1228", "1229",                    "1230", "1231"
               ];

//enter short days in the form eg 03/06 as 036:hours
var short_days = { "012":"8 am - 4:30 pm", 
                   "013":"8 am - 4:30 pm",
                   "014":"8 am - 4:30 pm",
                   "032":"8 am - 4:30 pm", 
                   "035":"8 am - 4:30 pm",
                   "036":"8 am - 4:30 pm", 
                   "037":"8 am - 4:30 pm",
                   "038":"8 am - 4:30 pm", 
                   "039":"8 am - 4:30 pm",
                   "0415":"1 pm - 1 am", 
                   "0416":"7:30 am - 1 am", 
                   "0417":"7:30 am - 1 am", 
                   "0418":"7:30 am - 1 am", 
                   "0419":"7:30 am - 4:30 pm", 
                   "0420":"7:30 am - 4:30 pm", 
                   "0423":"8 am - 4:30 pm", 
                   "0424":"8 am - 4:30 pm", 
                   "0425":"8 am - 4:30 pm",
                   "0426":"8 am - 4:30 pm", 
                   "0427":"8 am - 4:30 pm", 
                   "0524":"7:30 am - 4:30 pm", 
                   "0525":"8 am - 4:30 pm", 
                   "1119":"8 am - 4:30 pm",
                   "1120":"8 am - 4:30 pm",
                   "1121":"8 am - 4:30 pm", 
                   "1209":"1 pm - 1 am", 
                   "1210":"7:30 am - 1 am",
                   "1211":"7:30 am - 1 am",
                   "1212":"7:30 am - 1 am",
                   "1213":"7:30 am - 5 pm", 
                   "1214":"8 am - 4:30 pm",
                   "1216":"8 am - 4:30 pm", 
                   "1217":"8 am - 4:30 pm",
                   "1218":"8 am - 4:30 pm", 
                   "1219":"8 am - 4:30 pm",
                   "1220":"8 am - 4:30 pm", 
                   "1221":"8 am - 4:30 pm"
                };
```

Then again, given that I couldn't modify the backend code and the deployment strategy was nothing more than "emailing the files to Todd who would upload them live", this was the best way to modify the script.

### Redesigns

There were two times I was asked to redesign the library's webpage. One time for the homepage and another time for the InterLibrary Loan portal.

For the new homepage, the college was planning a massive redesign across all its websites. I did work on it up until I went to the UK for a class. By the time I came back to keep working on it, the site changed.

The InterLibrary Loan portal was a bigger project. I didn't have enough time to finish it, but it does look more modern now. Better yet, Todd was thankful because I introduced him to Bootstrap. I still wish I had finished the redesign.

### Routine Maintainance

Once in a while, I needed to fix on the webpage. The most interesting thing I had to fix was the carousel displaying new materials. After hours of trying to find the problem, it turned out that the jQuery script responsible for the carousel was out of date. It was part of [my CodePen page](https://codepen.io/faraixyz) since it let me livereload things.

### Other Plans

There were a few other things that were planned, like leveraging the library database's API to improve its user interface, make a database for archives and making a GUI for the hours script, but those got shelved because of other projects.

## Training

A big part of this job was training. I did this through training sessions and preparing documentation and evaluating technologies.

### Training Sessions

Once a semester, each member of the ELITE team had to present on something that would be beneficial for the library. In my time at ELITE, I presented on

* Password Managers
* Citation Managers
* Screen Casting
* Blogging platforms
* Printing
* Powerpoint Presentations (as a lightning talk)

While I wanted to present on a few things more ambitious and was frustrated each time I was told to pick something more "useful". Looking back at it now, I'm thankful that I did since I was forced to check my knowledge and simplify it for other people to understand. I wasn't perfect, but with each presentation, I got better. I do wish that I could present to patrons in general rather than just library staff but still, presenting was a valuable part of the job.

### Documentation

A great thing about the aforementioned training sessions is that we had to document whatever we talked about, from the proposal all the way to a summary about the thing I presented on. Let's take screencasting for example. I would start by writing a proposal on exactly what I wanted to cover, present on it and then write documentation on how to use it. I doubt Todd uploaded any of them, but we added them to our knowledge base which we could use to answer frequently asked questions.

### Evaluating Technology

I'd also be asked to evaluate different technologies and platforms that the library would then move to. These usually tied in with the training sessions (blogging platforms and password managers) but there was a time where I needed to find a replacement for one of the technologies the library used. Our internal wiki used a platform called Wikispaces which shut down and I had to find an alternative for it. I looked for alternatives and proposed them to Todd who would then pick one. I'm not sure what they're using now, however.

## Training Videos

A couple of times I was asked to make training videos. There are three videos I made and they're on YouTube if you wanna watch them. Here they are:

* [How to use the Collaborative Classroom](https://www.youtube.com/watch?v=XG58fyKdtWM)
* [Final Classroom Tutorial](https://www.youtube.com/watch?v=xQ_8uwE1W6g)
* [How To Cloud Print](https://www.youtube.com/watch?v=LxCvj19viAc)

## Exploration

Possibly the most interesting part of my job. Once in a while, I would have to try something I was unfamiliar with. At first, I was really grumpy and I wouldn't want to do it, but after a lot of patience, it would eventually work out. I've two examples of this, an ad and a bookmark.

### The Job Ad

![A maroon t-shirt with a name tag on the left lapel and the ELITE logo on the right lapel.](/images/elite-shirt.png)

The graphic designers weren't on campus for the summer, so Todd asked me to make a nice ad. I knew nothing about Illustrator and I was far too scared to try. On the one 4-hour shift I had, I was like "screw it" and spent four hours making the t-shirt you see above. I can't find the bigger ad, but I'm impressed at what a few hours of intense focus[^2] can do.

### The Vogel Library Bookmark

The second time I got to explore was when we were told to make something to print on the 3D printer. I really couldn't be bothered to come up with anything. I was stuck, but thankfully Todd suggested that I make a bookmark. With a few more hours of intense focus, I came up with a beautiful bookmark featuring the college's mascot, Sir Victor.

{{% scrollable %}}
<iframe width="700" height="280" src="https://www.tinkercad.com/embed/kLBnjz7TOFa?editbtn=1" frameborder="0" marginwidth="0" marginheight="0" scrolling="no"></iframe>
{{% /scrollable %}}

You can checkout [the bookmark on Tinkercad](https://www.tinkercad.com/things/kLBnjz7TOFa-vogel-bookmark) if you wanna play with it more.

There was another time I tried to make a useful print, but I failed miserably. I tried to make a hair comb to get women interested in 3D printing to[^3], but it was completely useless. I did make other useful 3D prints for patrons through the service I provided. 

## Service

As exciting as all the other stuff I've mentioned is, a big part of my job was serving patrons. A big part of serving patrons was checking out equipment like cameras, laptops and various computer accessories. This part of the job got annoying at times since I'd be in the zone working on one of the things mentioned in the previous section, interrupting my flow. Think this ~~xkcd~~ comic[^4].

{{% figure %}}
![Seven panel comic](/images/Programmer-Interrupted.png)
{{% figcaption %}}
[This Is Why You Shouldn't Interrupt a Programmer by Jason Heeris](https://heeris.id.au/2013/this-is-why-you-shouldnt-interrupt-a-programmer/)
<details>
<summary>Comic Transcript</summary>
Panel 1:Programmer looking at a monitor saying `if c == '.':backtrack`.

Panel 2: Programmer thinking of the code in panel 1.

Panel 3: Programmer thinks `...so if the current character is a comma, we set the back-tracking flag...`.

Panel 4, 5 & 6: Programmer thinking really hard about the code with elaborate flowcharts and diagrams.

Panel 7: Programmer gets interrupted by a colleague saying `hey, so I just sent you an email about that thing`, resulting in the programmer's mental mind map disappearing into a vortex.

Panel 7: Colleague walks away, leaving the programmer in the position they were in panel 1.
</details>
{{% /figcaption %}}
{{% /figure %}}

Another thing I did under service was set things up from conference calls to livestreams of the solar eclipse. Not too exciting, but a responsibility nonetheless.

At times, I was able to spend a lot of time helping a patron. Whether it's suggesting equipment, providing printing assistance, helping them understand a piece of software or even spending hours making a 3D print for them, I really enjoyed working with patrons to solve their problems. The most interesting problem I solved was helping a teacher set up one of the fancy classrooms that had just been built so that they could host a conference call. It took up an entire 4-hour shift and we had to come up with a convoluted setup, but it worked.

There's also a bunch of general library stuff I did, like update computers, clean cabinets and keep inventory.

## Conclusion

> Remember When You Wanted What You Currently Have?
>
> &ndash; Unknown

I've always found this quote rather strange. Rather than try to impart wisdom, it leaves it to you to figure it out. I've been thinking about this a lot in the months following my graduation[^5] in how I expected a lot from certain milestones, but it applies to this job.

I tried to get this job three times over two years and I was constantly rejected. When I got to college, I really didn't like food service and I wanted out so badly. When I saw the job posting for ELITE, I was all over it. It was in line with my major, which is among the best jobs you can get in college, along with jobs that give you lots of downtime.

Getting rejected twice was a bummer, but once I got the job which started on the 2nd of February, 2016, I was so happy. I planned on multiple web design projects, many training sessions and high impact work during the 10 odd hours I worked each week.

Working the job for two years, it didn't live up to the expectation I had set up for it. I was annoyed at the times I was asked to slow down to explain myself and help a patron who wanted another MacBook. And the expectation isn't just from the job&ndash; it's from me. I envisioned myself as a creative maverick, hosting grand training sessions, making great documentation and in the times the opportunity came to actually flex my college major, make a massive redesign to the library websites.

I didn't live up to that expectation, however. I would drag my feet at some projects, taking weeks to do something that would only need a few hours. I overlooked preparation and lacked the humility to understand that not everybody catches onto technologies as I do. I came related to patrons in an "efficient" manner without much interaction and only doing enough to get them what they needed. This echoes throughout my college experience.

Then again, I'm probably being a bit harsh on myself. I made an hours script that still works and helps patrons plan their studies. I've taken the time to share what I know while refining my knowledge. I've challenged myself at various points in my job to do things I didn't know and they turned out pretty well. As benign as lending MacBooks are, it's significant to the patrons who really need it; patrons who would then go on to write great essays, present brilliant presentations, do research and whatever else they needed to do. I also had great conversations with my fellow coworkers and full-time library staff. Sure, I could have done more but with what I did, I made a profound impact on the library.

The one thing that really made this job better was my boss Todd. I regret underappreciating him since he really did his best to help us grow. Even though we didn't know what we were doing, he encouraged us to learn. He stressed that we as ELITE members were literally paid to learn. He would routinely give us valuable feedback on the projects we made (for instance, avoiding the term click in regards to navigating UIs since not everyone can do that) and he cared for our wellbeing. The one big thing that he encouraged, however, is providing updates on the work we did and tracking our accomplishments so we can refer to them later like I'm doing now. I served as the perfect [vaudeville straight man](https://en.wikipedia.org/wiki/Straight_man) for his jokes, a role I have faithfully served for various teacher, professors and leaders since primary school.

I've lost the plot for the series My Git Revisited, but this job formed such a big aspect of my technical work in college that I couldn't ignore it. I've grown a lot through it and even though it didn't have as much coding as I would have hoped, I hope to carry the soft skills into my professional life.

[^1]: Well, I still worked in food service until graduation since I didn't have enough hours from the ELITE. I stopped working in food service for a while when I became an RA. As much as the food service job sucked, I made my first friends there and I got paid more.
[^2]: Wow, I guess there's something to the notion of [Deep Work](http://calnewport.com/books/deep-work/) after all.
[^3]: Interestingly, while more men placed orders, the women ordered more things at once.
[^4]: Not sure why I thought it was an xkcd comic.
[^5]: I've read a book called [Bad Advice by Dr. Venus Nicolino](http://talk2drv.com/bad-advice/) which really got me thinking about this. I don't want to explain too much right now since I want to give this book the proper attention it deserves in a future post, but there was a chapter on expectations. The general advice is that expectations always lead to disappointment along with how both of those things are bad. Dr. V proposes that rather than trying to avoid the disappointment of unmet expectations, we use disappointment to evaluate what we really expect. With that evaluation, you can then re-orient out expectations and actions to get to where you need to be.
