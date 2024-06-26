---
title: Hugo Now Includes a Default Render Hook for Links and Images
tech: [Hugo]
publishdate: 2024-05-03T22:29:08+02:00
draft: false
---

One big reason for the endless bikeshedding of my site are render hooks. While they're my favorite Hugo feature since they let you manipulate how markdown elements are rendered. Some uses of these are:

* adding width and height attributes to images,
* adding attributes to links,
* modifying how headings are rendered,
* along with whatever your imagination can think off.

Getting the details is tricky and took a lot of time. Thankfully, I discovered that Hugo has added default render hooks for [links](https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/_default/_markup/render-link.html) and [images](https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/_default/_markup/render-image.html).

Although they don't do everything that I want to right now they're a good starting point since they provide robust linking (using assets for images and ref for images) which reduce the odds of broken references.
