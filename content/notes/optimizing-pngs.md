---
title: How I Optimize PNGs
date: 2021-03-30T22:36:16+0200
lastmod: 2024-03-13T20:10:05+02:00
description: A short look at how I make PNGs smaller.
tech: [Images]
draft: false
---

**Update 13 March 2024:** I just use OxiPNG [Squoosh](/content/notes/squoosh.md) now. It's so much easier.
___

Here's how I optimize images in three steps:

1. **Resize the image using [ImageMagick](https://imagemagick.org/index.php)** to the desired sizes. The size I usually convert to is a 240px width image for small screen devices like [feature phones](https://en.wikipedia.org/wiki/Feature_phone) that fit the media query of `(max-width: 400px) and (-webkit-device-pixel-ratio: 1)`.
    * If it's a non-photogenic image inside a JPEG, I convert the image sizes to PNG using it.
    * If I'm converting an SVG, I use [Inkscape](https://inkscape.org/) (specifically [inkscape-cli](https://wiki.inkscape.org/wiki/index.php/Using_the_Command_Line)) since it's very good at rendering SVGs.
2. **Use [CompressPNG.com](https://compresspng.com) to restrict the color palette** as much as I can using a slider. This makes a massive difference in file sizes.
3. Finally, I then **use [ZopfliPNG](https://github.com/google/zopfli/blob/master/README.zopflipng) to recompress the PNG** for a slight size reduction. PNGs use some sort of DEFLATE compression algorithm to compress all the image data—Zopfli is a <q>very good, but slow</q> implementation of DEFLATE. It's a ~7% reduction which is just a handful of kilobytes.
4. Depending on the file size reduction and quality, I might also **convert it to Lossless WebP or AVIF**. This isn't as common since PNGs ae really good at non photographic images.

This process is based on my naive understanding of how PNGs work. I want to make a comprehensive post on how PNGs work and on how to use that understanding to better compress PNGs. There's a lot about the compression techniques, color indexing, sampling and the like.

## Glossary

non-photographic image
:   not a photo like illustrations, graphics and diagrams.
