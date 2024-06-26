---
title: figure.html and figcaption.html Shortcodes
linktitle: "`figure.html` and `figcaption.html` Shortcodes"
description: Shortcodes which help with handling figures.
publishdate: 2023-07-21T22:37:53+02:00
tech: [hugo]
draft: false
---

Though the `<figure>`/`<figcaption>` elements are typically used for annotated images, but they don't have to be. Instead of assuming that figures will always be images, this lets you specify markdown between a `{{%/* figure */%}}`/`{{%/* figcaption */%}}` block along with optional attributes for the respective HTML elements.

## Source Code

Except for the tag name, these shortcodes are the exact same. I'm wondering if I should just make a generic block shortcode which just changes the tag name.

### `figure.html` {#figure-html-src}

```go-html-template
{{< showFile path="/layouts/shortcodes/figure.html" >}}
```

### `figcaption.html` {#figcaption-html-src}

```go-html-template
{{< showFile path="/layouts/shortcodes/figcaption.html" >}}
```

## TODO

* Allow for non-closing shortcodes. Main blocker is [there doesn't seem to be a way to detect if a shortcode is a block](https://discourse.gohugo.io/t/how-to-check-if-inner-is-empty/28639) or not.
