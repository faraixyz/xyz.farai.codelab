---
title: QLapse Revisited
description: On the time I decided to try and make a Chrome Extension over a livestream
date: 2019-01-09
lastmod: 2019-02-15
series: [my-git-revisited]
draft: false
---

One random night during my Quora days, I saw a question about the things that suck about Quora. One person mentioned Quora's piss poor UI (which it still has) and how annoying it was not to be able to collapse an answer. Given this person had prominent advice on getting noticed companies, I thought it would be a great way to apply the advice she had on building personal projects to solve her problem by making [QLapse](https://github.com/faraixyz/farais-code-graveyard/tree/master/QLapse), a Chrome Extension to collapse answers on Quora.

At the time I was still propping up my personal brand and I decided to make this extension during a live-stream on YouTube. I remember making a Reddit post on [/r/learnprogramming](https://www.reddit.com/r/learnprogramming/) asking if anyone would be interested in watching me make it to which I got a resounding yes[^1]. The next day when I decided to host the live stream, only 2 people showed up.

No problem, I'd make the extension as I planned to. at the time I had already made a Chrome extension, [QuickPush](/content/notes/quickpush.md).

There wasn't a whole lot to this although it took me 4 hours to make it with the help of jQuery[^2]. Essentially, I had to poll the page to add an event handler to new answers that I scrolled past. This event handler would respond to a double-click and either collapse or expand an answer.

```js
//content.js
//TODO
// 1. Collapse answers from answer page
// 2. Collapse answers from topics

$(document).ready(function(){
var answers = [];
var answerlen = answers.length;

function poll(){
  answers = $(".feed_type_answer");
  for(var i = answerlen; i<answers.length;i++){
     answers[i].addEventListener("dblclick", hey);
  }
  answerlen = answers.length;
}

function hey(){
  //Collapses the answer
  var wah = jQuery(this).find(".Expandable.SimpleToggle.Toggle.AnswerInFeedExpandable.AnswerExpandable");
  $("#" + wah[0].id).removeClass("hidden");
  $("#" + wah[1].id).addClass("hidden");
  //var morebut = jQuery(this).find(".more_link")[0];
  this.addEventListener("click", function(){morel(wah)});
}
function morel(block){
  //expands collapsed answer
  $("#" + block[0].id).addClass("hidden");
  $("#" + block[1].id).removeClass("hidden");
}
  
var answerPolls = setInterval(poll, 2000);
});
```

With 2 years of hindsight, this is just awful. I had a whole lot of dumb variable and function names. Remember how I said this took 4 hours? Well, most of that was spent identifying how exactly an answer is collapsed and expanded. Given Quora's hostility towards web scraping, they make their web structure as convoluted as possible.

At the end of the 4 hours, I had something that seemed to work. However, as the TODOs show, this only worked on the home feed and I'd have to adapt this to other pages containing answers.  Since this seemed to work, the website's structure changed, breaking this extension and making it useless.

This was a good way to learn about polling in JavaScript with `setInterval` and the web scrapping skills I picked up here came in handy later in my academic career. So even though this script doesn't work anymore, the lessons I got out of this and the experience I gained are still with me.

[^1]: Top tip. Don't ask people if they want a piece of content. Just make it and let us know what you did. While I get the need to test the waters to see if your time is worth it or you might want to find out exactly what to talk about, you'll learn a lot by just starting and sharing what you've made.
[^2]: In the only negative comment I got on the channel, someone mentioned that this could be done in an hour. This is true, but my JS was still shaky at the time and I wasn't that great on live-stream.
