---
title: scrollable.html
date: 2023-08-13T18:05:36+02:00
draft: false
---

Not much here, just making divs scrollable. Make sure to add a label, [you need it](https://adrianroselli.com/2020/11/under-engineered-responsive-tables.html).<!--more--> In that case, it also means that all my code blocks probably need labels as well...

## Source Code

```go-html-template
{{< showFile path="/layouts/shortcodes/scrollable.html" >}}
```

Also uses this css

```css
.scrollable {
    overflow: auto;
}
```
