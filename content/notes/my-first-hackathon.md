---
title: "My First Hackathon"
date: 2015-12-09
lastmod: 2023-07-21
description: Where I write about the first hackathon I attended in 2015 at HackISU in Ames, Iowa.
tags: [hackathons]
notes:
    - date: 2023-07-21
      notes: My experiences at hackathons didn't go well except for [Uncommon Hacks in 2017](/content/notes/uncommon-hacks-2017.md) where our team won a prize for Most Uncommon project in line with the hackathon's vibes.
draft: false
---

Having earned my driver's license over the summer, I was now free to drive wherever I want, whenever I want. Of the places I wanted to drive to were hackathons. With the power of Google, I came across [Major League Hacking (MLH)](https://mlh.io/). As the "official student hackathon league", they are responsible for sanctioning hackathons across universities worldwide. While browsing their hackathons in North America, I came across [HackISU](https://hackisu.org/) which was hosted by Iowa State University, not too far from me. Having read numerous articles as to why attending hackathons would be great for finding internship opportunities, I set aside a weekend to attend HackISU.  

Here's how it went.

## The Day Before - Preparation
The day before the hackathon, I packed the things I would use for the hackathon. Namely,

* My (broken) laptop,
* A rarely used Arduino starter kit,
* A 10,000 mAh battery bank,
* A spare battery for my Galaxy S5,
* A sleeping bag,
* A pillow,
* An unhealthy amount of energy drinks and Mountain Dew,
* A bunch of cables and
* Resume's for recruiters in case any of them want to give me an internship.

Having packed all that, I did my homework like the responsible[^1] college student I am 🤗.

## 4 pm: Driving to Iowa State
After Calculus class, I headed off to Ames, 100 miles away. It was kinda scary since it was my first long distance[^2] drive. Since I'm writing this article, you can assume that I made it alive. After getting overtaken by only everyone, being scared of driving in the and navigating the <abbr title="Iowa State University">ISU</abbr> campus like a lunatic, I made it to the HackISU.

## 7pm: Registration and Dinner
Registration was fine although they ran out of t-shirts. Having registered, I looked around to see what everyone else was and I got sad. Everyone seemed to have an idea as to what they were working on. Moments later, the event started and they went over the main agenda, the rules and code of conduct, the sponsors and the prizes. After that, we had pizza from Papa John's.

## 8 pm: Let the Hacking Begin!
After dinner, I had to look for a team. It wasn't easy since most of the attendees were students at <abbr title="Iowa State University">ISU</abbr>, they already had their teams. I walked around the building where I stopped by the Hardware Lab. At that point, I came up with the idea of sending a notification whenever someone knocked on a door. While discussing my idea with one of the lab technicians, another person (let's call him <abbr title="Electrical Engineering">EE</abbr> guy) came in who seemed to have a better grip on hardware than I did. I then decided to team up with EE guy to work on the project.

## 10 pm: Two Become Four
As the two of us, we found two other team members, making us four. Let's call these guys <abbr title="Computer Science">CS</abbr> Guy and <abbr title="Computer Engineering">CE</abbr> guy. We discussed many ideas from image recognition with [OpenCV](http://opencv.org/) to making a useless application like [Yo](http://www.justyo.co/). As we were finding an idea, an employee from [Rockwell Collins](http://www.rockwellcollins.com/) came to talk to us. We asked him if they were making drones for the US Government (as Rockwell happens to be a government contractor) and he pleaded the fifth[^3].

Right next to us was a team working on an interesting project. They were trying to make an incredibly safe version of hot potato which would give you a slight shock whenever a potato hits your hand. After talking to them about their project, I connected to the internet so I could be more helpful to the team.

## 11pm: Eurika!
We finally had our idea- a black bean turret which would be controlled using an Oculus DK2 <abbr title="virtual reality">VR</abbr> headset to aim and a Pebble Watch to fire. Not only did it involve the skills all of us were good with, we could learn a lot from making the project! Just as we solidified our idea, the MLH's hardware had arrived.

I went to get the VR headset and the Pebble Watch. While waiting, I got to talk to an employee from [Workiva](https://www.workiva.com/), a company which makes business productivity software, about our project. After talking to him, I got to check out the stuff we would need.  They also had other equipment, such as

* Amazon Fire Phones #SAD[^4]
* [SnowShoes](http://beta.snowshoestamp.com/) - pieces of plastic which allow for interactivity without RFID, Bluetooth etc.
* [Oculus DK2s](https://www3.oculus.com/en-us/dk2/) - a VR headset
* [Leap Motions](https://www.leapmotion.com/) - a fancy motion sensor
* [Pebble Watch Classic](https://www.amazon.com/dp/B00KX828DG?tag=faraixyz03-20) - The first ever smartwatch.
* [Nest Cam](https://nest.com/camera/meet-nest-cam/) - a wi-fi security camera
* [Myo](https://www.myo.com/) - a gesture control band[^5]
* [Muse](http://www.choosemuse.com/) - a brainwave sensing headband

Being able to use all that stuff was really cool, but we had to stick to the plan. I picked up DK2 and Pebble Watch, handed over my driver's license and credit card, and returned to hacking.

## 12am: High Hopes
With our stuff and the realization that my teammates could get a free DK2 at my expense, we got ready to hack. And we started off strong in our assigned responsibilities.

I would program the Pebble Watch, EE guy would program the turret, CS guy would work with the Rift and CE guy would find a way to put it all together.

Within minutes I was able to get program a "Hello World" Pebble app using Pebble's amazing cloud based IDE [CloudPebble](https://cloudpebble.net/). I was proud about this since I got something to work despite never having programmed in C.

Meanwhile, EE guy was able to design the 3D prints for the turret, which would shoot small airsoft pellets rather than black beans. CS guy was able to get the DK2 running on his laptop. As for CE guy... I didn't know what he was up to. He was a quiet guy so whatever he was doing could have been very important.

With this solid baseline, we now had to figure out how to stream video to the DK2. Getting videos to actually play on the DK2 was hard enough, what more an actual stream. Having had little sleep the night before and having to drive in the rain finally caught up to me, so I went to bed.

## 6:30 am: A Not-So-Rude Rude Awakening

I suddenly woke up at 6:30 am extremely groggy. I didn't wake up because of a tap on the shoulder or a First Call. It was a slight "wake up" by one of the volunteers. Yet I felt so horrible.

If that wasn't bad enough, the pace we had started off with had started to fade away. While EE guy had the stream going, it had really bad latency. CS guy went <abbr title="Absent without leave">AWOL</abbr> and I still had no idea what CE guy what doing.

"No big", I thought to myself. I mean, I got "Hello World" running on a Pebble Watch. How hard would it be to detect a flicked wrist? Very hard it turns out. While memory management was totally new to me since I spent most of my programming life with garbage collected languages, I got the hang of it.

As for trying to get accelerator data, that was a whole different beast. I then decided to use their source code, but after two hours of hacking away, I got nothing.

At this point, we decided to scrap this idea. CS Guy was still AWOL and since he took his laptop with him, we couldn't work on the VR part of this project. Fortunately, we still had the original idea of sending a mobile notification whenever someone knocks on the door.

With this sobering realization[^6], it was time to get Subway for lunch.

## 1 pm: Getting Advice and Making Progress
After lunch, I headed to the Rockwell Collins booth to get my resume critiqued. The advice I got was to;

* **Add an objective**- so that the recruiter knows what I'm looking for.
* **Fine tune the resume** for the job I'm applying for.
* **Fix the resume's layout**- so that relevant information is quickly pointed out by the recruiter.
* **Make more projects** without an internship or relevant work experience, projects would help me stand out.

While I'm thankful for the advice, I can't help but note that all the resume advice has been very contradictory. Some want an objective, others don't. Some want projects on top, others want it on the bottom. Some love to see volunteering, others couldn't care less.

After the chat with the engineers, I went back to see what EE guy was doing. Turns out he was able to get the Arduino to pick up the door knock with the help of an oscilloscope[^7] and a piezo element[^8]. It wasn't perfect, but it was amazing what he could come up with.

I went back to CE guy who was trying to get an a "Hello World" application to run on Android, which was really hard. I mean, [@iamdeveloper](https://web.archive.org/web/20230629025517/twitter.com/iamdevloper/) gets it.

> “Hello World” in Android development is 3 days of trawling through documentation, heavy cursing and an existential crisis.
> 
> <cite>[I am Developer (@iamdeveloper) on <date datetime="2015-10-20">October 20, 2015</date>](https://web.archive.org/web/20230717184436/https://twitter.com/iamdevloper/status/656417508996452354)

It didn't help that my phone wouldn't connect to my computer in order to install the application.

## 5pm: Giving Up

We finally got the "Hello World" app running, but we had no idea how to work with push notifications. At this point, I gave up since this project was going nowhere. To celebrate my lack of will, I went to Buffalo Wild Wings and Starbucks. Once I came back, I messed around for hours, checking in on CE Guy and EE Guy every now and then.

EE Guy came to me since he needed help setting up the server. I didn't know a thing about servers, but a hacker from another team did, so they helped EE Guy. EE Guy got annoyed with the whole server setup thing and decided to implement what he learned from a side project.

## 11 pm: Spying on Other Teams

I was in full "shove it" mode, so I decided to see what everyone else was working on. Some of the things I saw were

* a speedometer for a bicycle,
* Craigslist for textbooks,
* VR music kit,
* a Redbox-like8 DVD dispenser and,
* a Chrome Game of [Wiki Races](http://thewikigame.com/)

The Wiki Races caught my attention since it was being made by high school students. Seeing the high school students with all this drive made me regret the time I spent as a kid. Then again, I ran a small business in high school, so that makes up for it.

At this time, there was no way I could accomplish anything. EE Guy was getting incredibly frustrated with everything. When we went through the [DevPost listing](https://devpost.com/software/oculus-turret)[^9], he cracked me up with stuff like this;

> **Me**: What was the best thing that happened in at this hackathon?
> 
> **EE Guy**: The windows are still intact and our laptops are in one piece

With the remaining time, I did random stuff, like reset my phone (which was so worth it)! I checked on CE guy who was still trying to get "Hello World" to work and I decided to catch up on sleep.

## 8 am: Another Rude Awakening...And Projects

While I wasn't woken up violently, I was still incredibly groggy. CS Guy was still AWOL and EE Guy also went AWOL. I guess he finally snapped. Fortunately for us, the project worked...for two minutes! Ah well ¯\\_(ツ)_/¯, I guess we'll have to go around and see what [everyone else made](https://hack-isu-2015.devpost.com/submissions) which was the following

* **[Feed Me](https://devpost.com/software/feedme-d6su1o)**:  An app that orders food for you after asking two short questions.
* **[A YouTube Playlist Manager](https://devpost.com/software/youque)** - #meh[^10]
* **Get Me Food**- Similar to the [Amazon Dash Button](https://www.amazon.com/b/?node=10667898011&sort=date-desc-rank&lo=digital-text), the only difference is that it's made for a college student's budget.
* **[MoBlocksMoProblems](https://devpost.com/software/mobblocksmoproblems-l95y21)**- These guys made a new mineral. A diamond sword I think.
* **[BookBuddy](https://devpost.com/software/bookbuddy)**- Craigslist for Textbooks, complete with messaging and Vemno API Integration. I really hope this grows to become something bigger than just as weekend hack given how great the project is as well as the team members.
* **[BOT](https://devpost.com/software/bot-8qec9n)**- Cool toy that comes with NFC enabled cards which tell it to dance.
* **[BalanceBot](https://devpost.com/software/balancebot)**- a toy which never topples over.
* **[MimeSound](https://devpost.com/software/mimesound)**- Think GarageBand for VR
* **[SafeTap](https://devpost.com/software/abcount-chn9vw)**-  A Pebble app that lets you check in with your friends, if you don't check in at a certain time, a missing report is sent.
* **[Cybox](https://devpost.com/software/cybox-wto8zd)**- a personalized version of Redbox Boxes. Apparently, the creator has been wanting to make this for a long time.
* **[OffKey](https://devpost.com/software/offkey)**- I had a hard time understanding this one. Something to do with encryption I think.
* **[Tweet-Mapper](https://devpost.com/software/tweet-mapper)**- Performs sentiment analysis on tweets.
* **Holographic Fighting Game**- I never knew that you could make holograms from a monitor and some glass...
* **[The Boarding Firefly](https://devpost.com/software/the-boarding-firefly)** - Cool RGB longboard

All the projects can be found [here](https://hack-isu-2015.devpost.com/submissions). The projects which won awards were;

* [BookBuddy](https://devpost.com/software/bookbuddy)
* [The Boarding Firefly](https://devpost.com/software/the-boarding-firefly)
* [BOT](https://devpost.com/software/bot-8qec9n)
* [BalanceBot](https://devpost.com/software/balancebot)
* [OffKey](https://devpost.com/software/offkey) and
* [MimeSound](https://devpost.com/software/mimesound)

## Reflecting on My First Hackathon

For my first hackathon, I did poorly since I didn't make anything and I gave up too easily. What this hackathon showed me was how much there is to learn. I mean, there are so many frameworks to learn, APIs to use and gadgets to hack. If I want to be of some value to an employer, I've got to make the most of college.

I also got exposed to a more vibrant tech/CS/engineering/hacking community which I don't get at my college. While I'm still socially awkward, I can assure myself that everyone else is socially awkward so my poor communication skills are met with more poor communication skills[^11].

From hackathons, I'm expecting to

* find a vibrant tech community,
* make something cool over the course of a weekend,
* win something after making the aforementioned,
* make some friends,
* learn something new,
* get employers to check me out,
* have fun and
* eat good food

## What's Next?
This semester, I also got to go to [MinneHack](http://minnehack.io/) hosted by the University of Minnesota in the Twin Cities (Minneapolis-Saint Paul, Minnesota). I still didn't make anything, but I met some really cool people.

Next semester, I'm hoping to go to HackISU at ISU again as well as [SwampHacks](http://2017.swamphacks.com/) at the University of Florida. Hopefully, I'll make some cool stuff that I can tell you about.

[^1]: I wish...
[^2]: inb4 "I'll have you know that I've driven 12 hours from Somerandomplace, Iowa to $big_city".
[^3]: "Pleading the fifth" refers to the [Fifth Amendment to the United States Constitution](https://www.constituteproject.org/constitution/United_States_of_America_1992#139) which gives one the right not to testify against themselves in criminal cases. In other words, refusing to answer questions that might result in self-incrimination.
[^4]: While this post was "published" in 2015, this post was revised in 2017 where [Donald Trump became the 45<sup>th</sup> President of the United States](https://nyti.ms/2k4lSJa) after a rather...unique campaign. Part of that campaign involved Trump's idiosyncratic use of [tweets](http://www.trumptwitterarchive.com/), some of which express his feelings of [sadness](http://knowyourmeme.com/memes/donald-trump-s-sad-tweets) at some facet of American governance Basically, I didn't have any predictive meme capabilities allowing me to make a joke before it was used.
[^5]: In hindsight, using the Myo Band would have worked better than the Pebble Watch.
[^6]: More like a reminder...
[^7]: An <dfn>[oscilloscope](https://www.wikipedia.org/wiki/Oscilloscope)</dfn> is an instrument that allows you inspect electrical signals and how they change over time.
[^8]: A <dfn>[pierzo element](https://en.wikipedia.org/wiki/Piezoelectric_sensor)</dfn> is a sensor that measures pressure, acceleration, temperature and strain using the [pierzoelectric effect](https://en.wikipedia.org/wiki/Piezoelectricity).
[^9]: [Devpost](https://devpost.com) is an integral part of hackathons. It allows you create your team, submit your project and see what other people have made.
[^10]: At least they made something...
[^11]: As much as I would like this to be true, I can't help but think of this piece of wisdom from Reddit. "If everywhere you go smells like shit, check your shoes". I really need to level up my social skills.
