---
title: Site's Configuration
description: How my site is configured.
tech: [Hugo]
lastmod: 2024-06-22T22:11:24+02:00
draft: false
---

This post outlines this site's configuration.

## Dates

```yml
frontmatter:
  date:
    - date
    - publishdate
    - lastmod
  publishdate:
    - publishdate
    - date
  lastmod:
    - lastmod
    - publishdate
    - date
```

This differs from the default configuration because of my needs:

* `publishdate` is the date when the post is published. If `date` is also there then it serves as the date when a post has been republished.
* `date` is the date when a post has been originally published. Defaults to `publishdate`. It also has `lastmod` so I can list updated posts on the [archive page](/content/archives/_index.md).
* `lastmod` is when a post was last updated. Falls back to `publishdate` then `date`.

My hope in doing this is to allow a post to have a publish date, republished date and updated date. I'm still trying to figure out how to render this on a page however.

## Markup

```yml
markup:
  goldmark:
    extensions:
      extras:
        insert:
          enable: true
        mark:
          enable: true
        subscript:
          enable: true
        superscript:
          enable: true
    parser:
      attribute:
        block: true
      wrapStandAloneimageWithinParagraph: true
    renderer:
      unsafe: true
    renderHooks:
      image:
        enableDefault: true
      link:
        enableDefault: true
```

There's a lot here but in short

* `extensions` enables [extended markdown syntax](https://github.com/gohugoio/hugo-goldmark-extensions?tab=readme-ov-file#extras-extension) like `<ins>`, `<mark>`, `<sub>` and `<sup>` elements.
* `parser` enables [block attributes](https://gohugo.io/content-management/markdown-attributes/#block-elements) which lets you specify attributes for markdown in curly brackets. The `wrapStandAloneimageWithinParagraph` prevents Hugo from wrapping images without surrounding elements within a block from being wrapped in a `<p>` tag so you can use block attributes with them.
* `renderer` with `unsafe: true` prevents raw HTML from being escaped in markdown files.
* `renderHooks` makes use of Hugo's default [render hooks](https://gohugo.io/render-hooks/introduction/) which are good enough to start with.

## Modules

```yml
module:
  mounts:
    - source: assets
      target: assets
    - source: images
      target: assets/images
    - source: files
      target: assets/files
```

This maps the `/images/` and `/files/` folders to the assets folder which allows them to be accessed as a [resource](https://gohugo.io/methods/page/resources/).
