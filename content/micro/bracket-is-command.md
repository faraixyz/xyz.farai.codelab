---
title: When Using The Test Command ([]) In Bash, Don't Forget To Put Spaces!
publishdate: 2024-03-17T21:15:00+02:00
tags: [til]
tech: [bash]
draft: false
---


I had a tiny bug while I was trying to set up my image processing build process. I needed to check if a file exists so I did something like this:

```sh
if [ -f path/to/file];then
    #...
fi
```

Looks fine except I got an error saying that `]` was missing even though it was there. Turns out that you need to put a space before and after the brackets because the brackets are an actual command, specifically [`test`](https://www.man7.org/linux/man-pages/man1/test.1.html), like this:

```sh
if [ -f path/to/file ];then
    #...
fi
```

Subtle, but worth watching out for!
