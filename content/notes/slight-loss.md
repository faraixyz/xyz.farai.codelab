---
title: I Wanna Know How Much Image Quality Do You Lose When You Attempt To Encode Images Nearly Losslessly
publishdate: 2024-06-24T20:28:28+02:00
description: How much quality can I remove from an image without it being noticed?
tags: [questions]
tech: [images]
draft: false
---

When it comes to reducing image sizes, the first thing you need to consider is whether the image is "photographic" or "non-photographic" as it will affect the compression techniques and formats you can take advantage of. Photographic means like a picture and non-photographic are images with illustrations, logo, screenshots and the like. Photographic images require "lossy" compression techniques which sacrifice image quality to reduce file sizes, though it shouldn't be too bad if you're doing it correctly. Non-photographic images on the other hand work better with lossless compression since losing quality in such images is more jaring were a lossy technique used. As much as I'm trying to make a clear distinction between the two image types, it isn't clear cut. What if you use a lossy compression technique but the result looks similar to the original lossless version.

One thing I've noticed when using [Squoosh](https://squoosh.app), an online image compression tool, they have an option called "slight loss" when you convert some images losslessly. WebP does this through the `near_lossless` switch and JPEG XL defaults to providing "visually lossless" quality when compressing images losslessly along with a "distance" switch which specifies how "far" away in quality you want to be from the source image. In theory this makes sense. Losslessly compressed images tend to be larger than lossily compressed ones. Sounds bad, but one might have to use lossless compression if losing quality is unacceptable. Thing is, you can objectivley take something away which can't be picked out without extreme pixel peeping. Given that, you should be able to maintain *perceived* quality even if it isn't mathematically similar, in theory.

I do this already by indexing the colors in PNGs. For instance, [xkcd](https://xkcd.com) comics are typically 2 colors, why does [this one](https://xkcd.com/356/) come with 64? Turns out having 2 colors makes the image look terrible and removes a color, but using 30 colors instead brought the filesize down to 30KB, although using 64 brought it to 40KB so IDK.

To that end, I wanted to know how much you can take away from a lossless image before the drop in quality becomes unacceptable, specifically by using the `near_lossless` and "visually lossless" settings. This note was harder to write than I thought...
