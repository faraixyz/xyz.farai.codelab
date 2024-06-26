---
title: Make Sure To Set Your Inputs and Buttons To At Least 16px or Safari will Zoom Into Them
description: At least zoom out once I'm done.
tags: [bugs, a11y, til]
tech: [webkit, css]
publishdate: 2023-10-02T05:09:57+02:00
lastmod: 2024-04-29T07:23:57+02:00
draft: false
---

I was working on adding a search page and I noticed that iOS Safari was zooming into the inputs. I assumed that this was for accessibility, which is great but it wouldn't zoom out again once I was done.

{{% figure %}}
<video src="{{< absURL `/videos/safari-input-zoom.264.mp4` >}}" controls width=300px></video>
{{% figcaption %}}
[Download video [514 KB]](/videos/safari-input-zoom.264.mp4)
{{% /figcaption %}}
{{% /figure %}}

Thankfully, [many people better at CSS than me](https://defensivecss.dev/tip/input-zoom-safari/) [have also had this problem](https://web.archive.org/web/20230224014348/https://twitter.com/joshwcomeau/status/1379782931116351490) to which the solution is to set the `font-size` of the inputs to at least 16px:

```css
input, button {
    font-size: 16px;
}
```

1rem will do, but you probably don't want to assume that it'll always be the case. Better yet, you can inherit all the font styles like [Josh Comeau](https://www.joshwcomeau.com/css/custom-css-reset/) does:

```css
input, button, textarea, select {
    font: inherit:
}
```
