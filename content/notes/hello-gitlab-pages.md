---
title: Moving from Github Pages to Gitlab Pages
date: 2017-08-13
lastmod: 2023-08-17T13:09:15+02:00
description: Up until now, I've hosted my personal website on GitHub Pages and I have few complaints.
notes:
  - date: 2024-08-17
    note: Since writing this, I went to GitHub Pages and I've also flirted with Netlify, Vercel, Render and Cloudflare Pages.
draft: false
---

Up until now, I've hosted my personal website on GitHub Pages and I have few complaints. I mean, all I need to do is provide either some HTML files or a Jekyll website, add it to a git repository named `fgandiya.github.io` and push it whenever there's something new. Better still, I can host my website using my domain, for free- a domain I got for free in the GitHub Education Pack[^1].

There are a few limitations, however. For one, the only supported site generator is vanilla Jekyll with a limited set of plugins. Also, there's no HTTPS for custom domains. While you could just build the site and track the built files and use CloudFlare to get HTTPS, it becomes a mess to manage. 

GitLab however, supports any static site generator with whatever plugins you want *and* it supports HTTPS on custom domains. There's a catch to this added functionality- it's harder to use.

## Working With Gitlab's CI

The reason it has support for any static site generator is that you need to tell Gitlab how to use it. This done by specifying a `.gitlab-ci.yml` which Gitlab will then run on its CI/CD pipeline[^2]. The `.gitlab-ci.yml` file contains tasks for Gitlab's CI to run with each task. In my case, I used the following `.gitlab-ci.yml` which is a template on the sample Jekyll Gitlab Pages project (annotations mine[^3]).

```yaml
# This file is a template and might need editing before it works on your project.
# Template project: https://gitlab.com/pages/jekyll
# Docs: https://docs.gitlab.com/ce/pages/
image: ruby:2.3 # a Ruby optimized docker image will be used to run the pipeline

variables: # defines the environment variables 
  JEKYLL_ENV: production

before_script: # setup stage
- bundle install #installs the dependencies defined in Gemfile using bundle

test: # test stage
  stage: test
  script:
  - bundle exec jekyll build -d test
  artifacts:
    paths:
    - test # the directory created in this stage
  except:
  - master

pages: # stage responsible for building the website
  stage: deploy
  script:
  - bundle exec jekyll build -d public # builds the site in `public`
  artifacts:
    paths:
    - public # the directory needed to host the site
  only:
  - master
```

Because of this pipeline, virtually any static site generator can be used to build the website. This comes at the expense of build times. Github Pages with all its restrictions would update a site in under 10 seconds whereas Gitlab Pages takes at least a minute, mainly due to fetching dependencies and launching the container.

There are ways to speed this up, however. For one, you could install the plugins in the project's directory, specify the plugins path in the `_config.yml` file and eliminate the `before_script` target. Another thing you could do is just build the page into a folder and track it before pushing it to Gitlab, allowing you to have the pages stage's script at `mv _site public`. While these things would speed up build times, it defeats the purpose of CI.

When you have two-factor authentication enabled, you should create a private access token. In addition to letting you use the API on your own account, the private access token is needed in order to add a git remote via HTTPS as your password won't work because of the two-factor auth flow.

[^1]: ...before it expired and I got another free domain at a hackathon through Domain.com- a domain which is about to expire yet again to be replaced by the original domain that I actually had to buy This time around.
[^2]: You could use CI on Github (or any git repository host) through a third party like Circle CI, Jenkins or Travis CI. However, Gitlab.com has this functionality built in, making it slightly more convenient.
[^3]: Before I wrote this blog post, I thought that Gitlab's CI pipeline is something I would never understand because of how complex it seemed. While writing this blog post, Gitlab's CI made more sense. I guess that's the value of writing blog posts- it helps you solidify your understanding of a concept. 
