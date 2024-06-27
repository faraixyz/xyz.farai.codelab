---
title: I've Finally Found A Media Query for E-Ink Devices and It Doesn't Work
linkedtitle: "The Curious Case of the CSS Monochrome Media Query"
tech: [css]
tags: [e-readers]
publishdate: 2024-03-31T21:44:00+02:00
archives:
  - https://archive.ph/9Pqw2
  - https://web.archive.org/web/20240330060850/https://blog.stephaniestimac.com/posts/2024/03/css-monochrome-media-query/
link: https://blog.stephaniestimac.com/posts/2024/03/css-monochrome-media-query/
draft: false
---

`@media(monochrome)` of course!

I was looking for this to target e-ink displays like Kindles and my [Boox Poke 5](https://onyxboox.com/boox_poke5), mostly to make smaller images for such devices like how [Low Tech Website](https://solar.lowtechmagazine.com/about/the-solar-website/#:~:text=Dithered%20Images,-The), a website which runs on solar power, does it.

I tried [Steph's Monochrome Media demo](https://stephaniestimac.com/demos/monochrome/) on my Poke 5 and it didn't work using NeoBrowser, a Chrome rebranding. Taking a screenshot, it was in full color though I'm not sure that means much.

![A color screenshot of the device's interface with a webpage saying 'Your device doesn't support monochrome pixels' in red](/images/media-monochrome-demo.png)

Actual Chrome and Firefox Mobile didn't support this either.
