---
title: Uncommon Hacks 2017
date: 2017-01-14
lastmod: 2019-02-15
description: Uncommon Hacks 2017 was the most sucessful Hackathon I've been to ever. Here's why.
tags: [hackathons]
projects: [math-floor-it]
draft: false
---

On January 14-15, I went to [Uncommon Hacks](https://uncommonhacks.com/) hosted by the University of Chicago. Applying wasn't too difficult and given how (relatively) close Chicago was from where I live, I was more than happy to attend. Much like the post on My First Hackathon, this post will outline what it was like to have attended Uncommon Hacks.

## 03:45 am Breakthrough!

Having just woken up, I showered, packed my bag and updated my resume. I tried to print some copies, but the dorm printers ran out of toner. No worries, there might be a print shop near Polsky.

Anyways, that was the least of my concerns as I was prepared to drive 5 hours to Chicago since my standby flight was fully booked. Fortunately, the airport was along the way and it turns out that there were a handful of seats left so no drive. #yay.

## 07:45 am Off to Polsky

After an uneventful flight, I was able to buy a train ticket with transfer for $5. I tried to make a vlog, but that didn’t work out for a few reasons[^1],

* It’s hard to set up camera angles.
* Talking to a camera in a public space is really awkward.
* The sound from the GoPro is terrible with all the heaving and ruffling against my shirt.
* I realized that editing isn’t easy.
* When I tried to mount the GoPro to the train, one of the ushers told me that I wasn’t allowed to do so.

I guess vlogging isn’t my thing. Let me stick to text and videos of text right now. Also, I should be living the moment rather than capturing it at to you. Technically, this post is capturing the moment, but it’s asynchronous meaning that I can do stuff and report on it later.

After writing this section, I carried on reading Hidden Figures. So far, I’m amazed at how the author turning the history into a story rather than just telling you what went down. Expect a post with my thoughts on the book in a few weeks[^2].

## 09:13am Damn Printers

After taking the train and the bus, I was able to grab an Egg McMuffin and Hash Brown at McDonald’s as well as print out my resumes at a UPS store. I had some printing problems, but fortunately, Polsky was just across the road so I didn’t lose too much time.

## 09:33am Recharged

With resumes in hand, I walked over to Polsky to sign in, get a miniaturized nametag, a sticker, T-shirt and stuff about WiFi. Once logged in, I charged my phone using one of the power strips on the table.

After a while, I realized that the coveted power strip wasn’t plugged into power. Eh, whatevs, I can wait and besides, I’ve got a power bank. I also forgot my VR headset, Raspberry Pi and Arduino[^3] back on campus so I’ll have to settle on being the backend/dev ops guy.

As 10 am came past, some guys from Colorado came to the table. I went for some breakfast which was made up of coffee, a naartjie (mandarin) and croissant. About the naartjie, I tried asking around for the spelling which nobody knew before turning to Google which also didn’t know because of my terrible spelling. After some better queries (“orange-like fruit with peelable skin”), it turns out that the naartjie is Afrikaans for mandarin/clementine[^4].

Since I asked so many people for the spelling of naartjie, I started off some conversation[^5]. I also crashed into the guy who I hacked with the year before. With my social fix obtained and my table set up, I’m ready to hack.

## 10:15 am Career Fair and Meeting People

Seeing many people go to the one room, I decided to see what the was about. There I found few companies, most of which weren’t looking for interns[^6], let alone international students. On the plus side, there was lots of cool swag and there was even a guy in a space suit advertising a Bitcoin charity.

Since there wasn’t a whole lot to do, I went to the speed dating exercise to form a team. There, I was given a little slip of paper with a question I was to ask. The question I got was “M/F/K JavaScript, C++, PHP”[^7]. Strange question, much like the hackathon, but I met some cool people from the speed dating.

Eventually, I grouped with a team of 8 where we brainstormed ideas before we split into 2 4 person teams. Between the 8 of us, we went with two ideas, stuff with wireless beacons and a fun web app to show the price of speeding. Ultimately, I choose the latter idea since I was more comfortable with JavaScript than hardware.

The team I landed with had a guy from Kent State, a university which has a strong focus on fashion and tech with a department called TechStyles (hehe) and two ladies from UChicago, one of whom was attending their first hackathon. We all seemed to have the ability to search things out and understand JavaScript in some capacity, so I felt confident we'd be able to make something.

## 11:30am Brainstorming

With the teams set, we listened to the opening presentation which featured some slam dank poetry, reviewed a shoddy resume and helpful tips for the weekend. We then had lunch, which was a nice assortment of pasta[^8], all the while planning the silly web page.

Once lunch was out of the way, we started brainstorming as a group in addition to splitting up responsibilities, trading contact information and creating the GitHub repository. As for our responsibilities, two of us would focus on design and the rest of the group focusing on hooking up with Google Maps API and gathering data on speed traps and red light cameras.

Finding the data wasn't hard the City of Chicago lists all the s[peed traps and red light cameras](https://data.cityofchicago.org/Transportation/Speed-Camera-Locations/4i42-qv3h). It even gave us the ability to export it in many data formats like CSV and JSON. Thankfully, the documentation for the [Google Maps API](https://developers.google.com/maps/) was clear so it wasn’t hard to understand how the code worked as well as how to use them. With a rudimentary understanding of the API, we took time to learn more of it to draft paths and list the cameras.

While working, we met a mentor who had been programming for 42 years who had some interesting stories, like taking pictures of Ken Thompson (UNIX guy) and working with massive hard drives which acted up violently. He's also claimed to have made the first keylogger.

## 03:00 pm Shit, I should have paid attention

At this time, we as a team decided that it was beneficial to attend the workshop on Asynchronous JavaScript in ES 6[^9] since we would be making use of a couple of them. The talk itself covered were things that I was aware of so it felt like a waste of my time, although seeing what callbacks actually do was quite helpful tbh.

A few minutes after that talk, I needed to use the `jQuery.getJSON` function to read some of the data I imported. Simple enough, or so I thought. While I was able to read the data and pull of what I needed from it, it wouldn’t add elements to an array given code like this

```js
/*
the code used to load speed cam data
*/
var speedcams = [];
$.getJSON("data/speed-cam-locations.json", function(json){
    var locs = json.data;
        for(var i=0; i <= locs.length; i++){
            var pos = {lat:parseFloat(locs[i][12]), lng:parseFloat(locs[i][13])};
                var marker = new google.maps.Marker({
                    position:pos,
                    title:"Speed Camera"
                });
                speedcams.push(marker);
            }
        });
console.log(speedcams.length); //length is 0
```

After talking with the veteran hacker mentor, it turns out that it did add elements to the array, **however**, `$.getJSON` is an asynchronous function, meaning that the execution of `console.log(speedcams.length)` does not wait for the `$.getJSON`  call to finish. That means that the elements are added, it’s just that the code after `$.getJSON` is running based off of what it sees in `speedcams` as it is called, which has nothing[^10]. Basically, if I want to do stuff with `speedcams`, I’d have to either use it in a listener or do it right in the asynchronous call.

The next three hours was spent trying to make the asynchronous call synchronous (save it to a variable) and the same “empty” array would come up. I thought a promise would help, but I couldn’t get it in place. I guess I should have paid more attention presentation[^11]. Oh, Farai… At the same time, one of my team members went off to explore Chicago, and the other person working on picking up camera’s located on a path realized that `isLocationOnEdge()` wasn’t entirely accurate since camera’s far off of the path sometimes picked up and camera’s right over it wouldn’t register.

## 06:48pm Seems Legit...

Since this hackathon is...strange, they decided to bring in a fortune teller[^12]. Frustrated at the lack of progress, I decided to go to the fortune teller just ‘coz. The fortune was too generic to be angry with, putting it at a C- (loads of BS, but it can be convincing). After the fortune teller, we head off for some Indian dinner which tasted really good[^13]. 

After dinner, I decided to ignore the async issue and focus on getting autocomplete search for the address, which was much easier to do. Soon after, I was integrating code from my teammates and solving merge conflicts, which went pretty well. Honestly, I’m glad that I’m making a project that is going somewhere unlike my previous hackathons where I would pull out halfway through[^14].

## 10:12pm Celery Man

At this point, I realized how much work I’ve been doing, so I decided to get a bit competitive. There was a celery eating contest which I entered thinking it would be easy given how quickly I eat food. Well… turns out that after not eating veggies for a while, eating celery is harder than it seems. I lost gracefully and went back to the desk to update the hackathon diary at the same time scaling back my duties from a hardcore hacker to an advisor since I needed to recharge and collect my incredibly muddy thoughts.

While at it, I helped my teammate switch from testing via the file system to running off of localhost[^15] to use AJAX functions because of the same origin policy. The organizers then hosted a super secret event where the tried to seance a Galaxy Note 7 before drilling it to ultimately brick it[^16].

I was planning on going to bed, but they had in some really delicious warm cookies and Dunkin’ Doughnuts Hot Chocolate. I forgot all my sleeping stuff in Waverly, but they have air mattresses. While I couldn’t get one, I found a very comfy spot to sleep at.


## 07:15am Terrible Sleep

While the chairs seemed comfy, the sleeping experience was anything but. For one, it was really cold. That coupled with the fact that I had no blanket made the sleep unbearable. I could only clock in about 2 and a half hours before I gave up, played on my phone, brushed my teeth and headed back to our table with the one lady on the team who was touching up the UI. Apparently, she also got under 3 hours of sleep for the same reason as me.

The other members arrive and for some odd reason, one of them were able to get a good seven hours of sleep. Now that we were a full team, we worked on polishing up the code. The time came around where we were supposed to create our DevPost listing describing the project, what we did, the problems we faced, our accomplishments and the prizes we were aiming for. We aimed for best beginner hack, <i lang="jp">Chindōgu</i>[^17] (prize for something which tries to solve a problem, yet it creates another), Madame Zande (the fortune teller. I don’t know man) and Most Uncommon.

## 12:00pm Lunch Time

At 12 pm, it was time to stop hacking, clean up and get some lunch. For lunch, they brought in some amazing Chinese food which I gladly took a whole plate of before going upstairs and meeting some other teams. One team from Colorado were all hardware guys, yet they were able to make an Android app that will gradually turn orange as Donald Trump tweets.

After lunch, we had a small session where we were introduced to the judges, all of whom had loads of experience. We even had a 5-year-old girl to judge the projects. With the small session, we headed off to our presentation table, set up and awaited the judges.

## 02:00pm Judgement ~~Day~~Hour

As we picked an optimal route for our app (to hide our bugs), we waited for the judges. One by one, we made our pitch, had some laughs, took questions, and observed dozens of WTF faces. After a while, I decided to explore what other teams did.

While the full list of projects made at Uncommon Hacks can be found here, these are some projects that I thought were pretty cool;

* A webcam that is able to read facial expressions.
* A location-based social media platform where you make posts based on where you are. Think writing on the toilet stall walls.
* Clippy on Android
* An Overly Attached Alexa
* A giant Teletubby
* A script that watches YouTube videos of people playing the piano and converts it into a MIDI file
* A Zen Garden and many others

All of the prizes that came out of this hackathon were very well done given the amount of time we had to make these projects. Even with all struggles along the way, all of us were able to work through them (or drastically limit the scope of the project)

## 03:00 Awards Ceremony

{{% figure %}}
![A picture of me with four other people](/images/winning-team.jpg)
{{% /figure %}}
{{% figcaption %}}
Our winning team. Taken from [the Uncommon Hacks Facebook Feed](https://www.facebook.com/uncommonhacks/photos/1565759120108433)
{{% /figcaption %}}

With the Expo over, we got ready for the awards ceremony. Before the awards were given out, they showcased the top 6 apps made over the weekend which were very well made. From great ideas to very well implemented ones, all of the top apps deserved to be there. As for our project Math.floor(it), we were able to scoop up two awards, one for best beginner hack as well as Most Uncommon for living up to the spirit of the hackathon.

Given how dank this hackathon is, the prizes they gave up were uncommon, to say the least. Besides the Nintendo Switch, Headphones and Echo Dots, most of the awards were...strange. Like some prizes were unicorn farts and a years supply of KIND bars. Somehow, we won the prize for Most Uncommon. Our prize was a muppet plant[^18] for some odd reason. I wish we got the unicorn fats instead.

After all the goodbyes were said, I went to Nandos, looked for a bus, headed to the airport, hustled for a seat before flying home and facing my many responsibilities back at college.

In all, I’m happy with the way this hackathon turned out. In all the other hackathon I’ve been to, I’ve never stayed behind for the entire event. Finishing the app (an award-winning one) is great validation. While I couldn’t hustle for an internship interview and I was incredibly socially awkward, I would say it was worthwhile, especially with how well organized (and uncommon), it was. I just wish that I sorted out my college responsibilities before going to the hackathon. For future hackathon, I hope to make more interesting projects and socialize better.

Next time, I’ll talk more about Math.floor(it) (now [online](/content/notes/math-floor-it.md)), and the process of making it. If you want a sneak peek, you can check out the [Git Repository](https://github.com/faraixyz/math-floor-it/), read the [DevPost listing](https://devpost.com/software/math-floor-it) or even play around with [the app itself](http://faraixyz.github.io/math-floor-it/). Just know that it only works in Chicago right now.

<hr>
Side Note: This post is just about 2800 words long, probably the longest article I have ever written on this blog. While I’ll write about Hackathons in the future, I probably won’t write one this long. I’ll probably write on the highlights and the general atmosphere rather than a play-by-play account.


[^1]: I don't know how people are confident enough to vlog out in public. Talking to a camera in public is a bit awkward and that's coming from me!
[^2]: I never got to it. I watched the movie however and it was amazing!
[^3]: Not like I know how to use them anyway...
[^4]: Now that I think of it, a lot of things I called stuff in Zimbabwe are Afrikaans words...
[^5]: It’s really hard to start a conversation with strangers unless someone dares to speak first. More on my social ineptitude later in this post.
[^6]: I guess sponsors only come to sponsor events. Shocker. Then again, last time I cam here, I had a great chat with a guy from Twillo, the internet phone people.
[^7]:  “M/F/K” being Marry, Fuck, Kill between the three options. Personally, I choose to kill PHP in line with the “PHP Sucks” meme, marry C++ since it's useful and fuck JavaScript since it's trendy so I assume it's sexy.
[^8]: From the hackathons I've been to, Uncommon Hacks have the best food hands down.
[^9]: I'm still stuck on ES 5. I mean, it works and I don't have to worry that much about browser support. inb4 Babel.
[^10]: I think this is called a race condition.
[^11]: Many of the problems I encounter while learning wouldn't be problems had I paid attention.
[^12]: Last year, they had a pancake guy who could imprint a picture on a pancake.
[^13]: A while back, hackathon food was just copious amounts of pizza and junk food. Given enough awareness about how unhealthy this is, some events have moved to get actual food, a motion I get on board with.
[^14]: tbf, it’s hard to get back to Wartburg with no car
[^15]: Using `python -m SimpleHTTPServer`or `http.server` in Python 3.
[^16]: I haven’t mentioned it till now but I find it hard to fit in here honestly, between my insane awkwardness (even for a nerd’s standard) and the general feeling of being ignored and speaking to air, I didn’t feel in place. I won’t go further here, but it’s something I really need to work on for a few years before being somewhat competent. Same with a lot of things. Better get to it.
[^17]: [<dfn>Chindōgu <i lang="jp">(珍道具)</i></dfn>](https://en.wikipedia.org/wiki/Chind%C5%8Dgu) is the art of inventing gadgets that attempt to solve problems, but make them worse. Basically this:<br>![A person eating a bowl of ramen with a fan connected to a battery between the chopsticks blowing the ramen](https://files.tofugu.com/articles/japan/2016-03-14-chindogu-japanese-inventions/noodle-cooler.jpg).
[^18]: It's a [chia pet](https://chia.com/).
