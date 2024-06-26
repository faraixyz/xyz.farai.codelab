---
title: My First Tech Interview
date: 2016-02-27
lastmod: 2019-01-2020
description: After 30+ applications and 4 career fairs, I've finally got called in for an interview by a dev shop located in Des Moines, Iowa.
tags: [tech-hiring, tech-career]
draft: false
---

After 30+ applications and 4 career fairs, I've finally got called in for an interview by a dev shop located in Des Moines, Iowa. 

## Finding the Company

I first met the company at [a hackathon](/content/notes/my-first-hackathon.md) they sponsored. Just two days after, I met them again at their booth at a career fair. When I tried to apply for an internship, they suggested I work on some projects to gain more experience before trying again[^1].

A few months later, I went to another career fair, met them yet again and to my surprise, they were willing to consider! Finally, all my hard work paid off.

## Interview Process

The interview process had three parts to it.

* A [pre-screening](#pre-screening),
* A [campus interview](#campus-interview)[^2] and,
* An [on-site interview](#on-site-interview)

### Pre Screening
A few days after the career fair, I was sent a Hackerrank Quiz[^3]. The quiz had two questions- FizzBuzz[^4] and a coin counting problem. I decided to solve the problems in Python 3, but after pair sum, only Python 2 was available.

The FizzBuzz problem was straight forward, although I nearly had bad flow control. As for the coin counting problem, it _seemed_ easy, but the approach I was using, which relied on a greedy approach[^5], that failed certain tests. The actual solution to this problem is to use a doubly nested loop to check all items until a certain combination equals the required sum.

Having submitted the quiz, they told me to go in for a campus interview a few days later.

### Campus Interview

At first, I thought the campus interview would be a phone interview. I didn't know I had to be at the university where the career fair was for the interview until the day of the interview. After my Windows Phone[^6] got me lost, and nearly crashing twice, I made it to the university **exactly on time**- as in, as soon as I sat to wait, they were calling in the next person. 

At the interview itself, they started off by asking which programming language I wanted to work with. I shouted out "Python", which they didn't know. I hesitated and decided to go with JavaScript which I was learning through [Free Code Camp](https://www.freecodecamp.org/). Having chosen a programming language, I was ready for the challenge.

For the challenge, I was asked to find a duplicate in an array. I was encouraged to think out loud and to ask for help when needed. My first approach was to sort an array, iterate it and see if the next index was different. If it was, I would return the element in that index. The interviewer told me that it was "slow" given it was running at O(n<sup>2</sup>). He then suggested using a data structure with constant time inserts and deletes.

"Dictionaries!" I thought to myself. Using a dictionary[^7], I implemented a way to insert each item into the dictionary using how frequently a value has occurred in the array. I would iterate over the dictionary and delete items with a frequency over one.

Still, this solution was O(n<sup>2</sup>) and it had a few other errors. I was then asked how I could improve performance where I then blanked out. In hindsight, the solution was obvious, but being the dumb kid I am, I never noticed that I could delete the item instead of incrementing its value. I made the change and passed the tests.

The interviewer said that there was a solution which didn't need a dictionary, allowing it to be done in constant memory (O(1)) and linear time. To do this, I would do an XOR add over the list which would delete duplicates[^8]. This solution didn't help my self-esteem since I didn't understand what was going on until my professor explained it to me[^9].

Before the interview ended, I asked about the testing framework used, [Mocha.js](http://mochajs.org/) as well as had a bit of small talk. After the interview, I ate some Panda Express before rushing back to campus since I was scheduled for work that day.

### On-Site Interview

The third interview had me driving to their offices in Des Moines where I got lost again. Once I arrived, I got a tour of their office, which had the programmers' standing desks, administrators offices and a conference room where I would have my interview. 

In the conference room, I was introduced to the engineers who would be testing me. The test itself wasn't really a test but more like an overview of [test-driven development or TDD](https://en.wikipedia.org/wiki/Test-driven_development). The assignment itself wasn't hard but being patient enough to go through the TDD process which involves writing a failing, doing the bare minimum to pass the test, testing again and repeating that until you make a full system, cleaning up your code as you go[^10]. I liked the interview since it didn't feel like an interview but it felt like the engineers were getting to know how I worked.

After the interview, the recruiter took me out for lunch at a nice cafe[^11]. We talked about our personal lives and he even mentioned how he (and other employees) got to read some of my blog posts. After lunch, he drove me back to the office so that I could go home.

## Conclusion

In all, I'm happy that I finally got the chance to prove myself. Granted many others got dozens of interviews in their freshman year, but this was a big deal for me. Hopefully, this will be the first of many interviews and even more offers.[^12]!

[^1]: Probably a nice way to say no.
[^2]: Since the career fair at my college isn't very big let alone tech-oriented, I have to go to a career fair another university. Because the interview was at that university, I need to dive back to that university for the interview.
[^3]: HackerRankis a company focused on competitive programming challenges, usually for screening tech applicants. 
[^4]: FizzBuzz is a coding challenge in which, given a number `n`, you need to iterate up to `n` printing `Fizz` if the number is divisible by 3, `Buzz` if the number is divisible by 5, FizzBuzz if it's divisible by both 3 and 5 and the number if it's divisible by neither 3 or 5. It's a simple problem, but many applicants struggle with it, usually, the placement of the `if` statement or not understanding the `%` operator. It's a meme in the programming community due to how it tends to infantize applicants.
[^5]: By [greedy](https://en.wikipedia.org/wiki/Greedy_algorithm) approach, I'm referring to the technique of making the optimal choice at each stage. For instance, with coin counting, a logical approach would be to give exact change by working down from the highest possible denomination at each step. This is fine with most currencies, but there are a few edge cases where you need a better solution. That better solution would make use of [dynamic programming](https://en.wikipedia.org/wiki/Dynamic_programming), which I've forgotten about. I need to revise the algorithms.
[^6]: My old phone, a Samsung Galaxy S5, broke after dropping it one too many times. Worse still the insurance cost $200 and I had one month until I could replace it. As an emergency measure, I picked up a Nokia Lumia 625. For $25, it's a really good phone. Long battery life, decent camera and snappy. My problems with it are the lack of apps on Windows Phone, the ridiculous memory constraints. To be fair, those same constraints allow the phone to be snappy and the terrible GPS which got me lost and snitches on me if I go over the speed limit.
[^7]: That's a hashmap in Python.
[^8]: An `XOR` is a logic gate which takes in two inputs and returns true only if only one if the values are true.
[^9]: Thinking back on this now, what's the point of flexing some super complex solution if you can't explain it to me? mxm.
[^10]: Funny enough, I read an [article](https://www.microsoft.com/en-us/research/blog/exploding-software-engineering-myths/) by Microsoft Research where they discovered that while TDD takes longer, it's less prone to error. Fair tradeoff.
[^11]: Apparently this is a very common (at least it was) recruitment practice for programmers.
[^12]: As if...
