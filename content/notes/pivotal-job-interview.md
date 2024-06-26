---
title: My Job Interview At Pivotal
date: 2019-06-29
lastmod: 2020-01-21
tags: [tech-hiring, tech-career]
description: This is about the first time I got a tech interview thanks to the strength of weak ties.\
draft: false
---

Thanks to a random stranger on the internet, I got to interview at Pivotal in San Francisco. Here's how it went.

## First Interview

The first interview had paired up with one of their engineers to implement a [set](https://en.wikipedia.org/wiki/Set_(abstract_data_type)).

I was aware of this thanks to Glassdoor so I spent a week looking into how to implement a Set. I figured that I'd need to implement an AVL tree as the underlining structure of a Set[^1]. I couldn't figure out tree rotations so I stuck with the naive approach of array manipulation.

Thankfully it went better than I had expected. Since they use TDD, the interview was slow paced. Failing test, laziest change, actual implementation, refactor, repeat for an hour. A few days later, the recruiter got back and I was on to the next round.

## Remote Pairing
Since a location wasn't specified on my application, I told them that I was okay with either San Francisco or New York. Instead of sending me on-site right away, they decided that it would be best to pair with one of their New York-based engineers to decide on whether to move on site or not. They were nice enough to send me some prep materials which were centered around Go. Once I got to the interview, I paired with one of their engineers to fix a bug on one of their Java Spring applications.

As a Python and JavaScript guy, I was taken aback a little. My only exposure to Java was an elective class I took where I made some crappy memory game and a few failed attempts at learning Android Development. Even though my Java was shaky, I was able to work with the engineer to fix the bug. Over the 4 hours, I got to ask a few questions about the companies culture as well as what it’s like working in New York.

After the interview, the engineer wrote some feedback which was good enough for me to move on sight. I talked with the interviewer about my experience, salary expectations[^2] and travel logistics.

## First Time in San Francisco

Just after graduation, I went to LA and Vegas with my family. I wanted LA and San Francisco but my sister insisted on Vegas and LA instead so I was excited that I got to go to San Francisco. The day before the interview, I got into San Francisco around 2 pm before I took the train to the hotel, which was conveniently placed across the road from Pivotal’s San Francisco offices[^3].

Since I came in early, I decided to watch the <cite>BlacKkKlansman</cite> which was an okay movie. Near the theatre was a mall I decided to check out. I heard that there was a robot barista by [Cafe X](https://www.cafexapp.com/) so I headed to get a Matcha Mocha served by a robot. While the Matcha Mocha had an interesting taste to it and at $3 there aren’t many complaints you could levy towards it, the robot is basically a gimmick. I was planning to go to the [Museum of Ice Cream](https://www.museumoficecream.com/), but it cost $35 for what amounts to an [‘Instagram Trap’ [Video]](https://www.youtube.com/watch?v=Qx_r-dP22Ps) so I headed for dinner. 

For dinner, I decided to eat at a [one of those Korean BBQ places [VIDEO]](https://www.youtube.com/watch?v=GTXP2FzQS94). It took hours to find a place I could eat at since most Korean BBQ places have 2 person minimums, but I eventually found [Carbon Grill](http://www.carbongrillsf.com/). On the Lyft there, I got to chat with someone who used to work in tech before he got carpal tunnel. I was going to have dinner with him to chat more, but he decided to eat elsewhere. As for the food, while I struggled to cook and eat with chopsticks[^4], it tasted really good. I then headed back to get some good rest before the interviews the next day.

## The Onsite Interviews

The next day, I checked out of the hotel and headed to Pivotal’s office right across the road. After meeting my host, I was invited for breakfast which they serve for their workers every day. I sat with the host and was joined with another person[^5] being interviewed along with my first interviewer. After breakfast, I headed down for one of their sprint meetings before my interview began.

For the first pairing interview, I worked on one of their APIs built with Ruby and Sinatra. Asides from a footnote in my internet programming class, I’ve never touched Ruby. It took a while to figure out what was going on but I got the hang of it, sort of. I think the task was barely completed by lunchtime where we modified a higher level test to figure out what was going on.

The office serves lunch to their workers once a week accompanied by a discussion. Apparently, they’ve hosted a chair startup before. Anyways, after lunch, I headed to the next pairing task. This time around, there was a very low-level system bug that needed fixing. The system was implemented in Go which I had an even dimmer idea of in spite of my attempt to learn it. While I did figure out what was going on thanks to what I learned in my computer networking class, I still had a lot of WTF moments.

After the interview, I said my goodbyes before wandering around SF until my midnight flight back to Michigan. In the time wandering SF, I had fried chicken and Mac for dinner and some actual waffles, with ice cream[^6]! I then headed back to Michigan eagerly awaiting a response.

## Response and Conclusion

Unfortunately, I didn’t get the job. After crying over it for a bit, I decided to apply for more jobs in hopes that something would come up (spoiler nothing did). Still, I think this was a good interview process. Even though I didn’t have a lot of experience with the programming languages used in the interviews, I was able to figure things out. While I don’t have a problem with pairing, it seems like you need to be a certain type of person to do it 8 hours a day. I like the experience of what their work days are actually like so I can experience the culture. The only improvement I could think of is getting paid since it was basically doing work (although the problems have already been solved). Then again, they’ve probably spent thousands of dollars interviewing me at that point.

Looking back on it, I kinda realize why I didn’t do so well. Remember the WTF moments I mentioned in the Go interview? I really wish I had a more systematic approach to addressing ambiguity rather than asking "what the fuck is going on" over and over. Not sure how to fix this but I think this might be the key to doing better at interviews.

[^1]: This isn't quite right. A better way to do this to work off of a hashmap, implemented with open addressing of an array with an AVL tree to handle collisions.
[^2]: Don’t say a number first. Try to get a range and decide if it’s acceptable. In California, they have to. I didn’t realize it and I thought they were being nice when I was being coy about giving salary expectations.
[^3]: Much closer than the Goldman Sachs interview across the river in another state.
[^4]: If you’re bad at using chopsticks you can either learn how to use them properly, get the kids chopsticks with a rubber band at the end or just humble yourself and ask for a fork. No big deal (in the US at least).
[^5]: The person worked at Google for 4 years before getting fed up with it. They mentioned how Wi-Fi connected buses are a ruse to make people work longer. Interestingly, I got another perspective at my Google Interviews. Stay tuned to learn what this perspective is In another post.
[^6]: One strange thing about the US is that they don’t do waffles properly. I’m used to them being a dessert item with ice cream rather than a breakfast item. Even worse, they even have [waffles with fried chicken](https://en.wikipedia.org/wiki/Chicken_and_waffles)😱. Not sure who decided to put them together.
