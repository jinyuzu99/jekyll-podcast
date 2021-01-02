# jekyll podcast

jekyll podcast generates audio podcast feed and note for jekyll.

## why jekyll podcast

uploading podcasts is not as easy as uploading videos, you have to own or borrow a web server to host your content.

there are a lot of platforms for people to upload podcasts, but some of them spend your money, some of them cannot be configured to your requirement.

although there are also some podcast holding solutions for jekyll, they are difficult to use. and they don't have a solution to generate web pages for your podcast.

to solve these problems, t build this configurable jekyll-podcast. you can host it on free jekyll services (like [github](https://github.com), [gitlab](https://gitlab.com)), then you can buy a better 🎙.

## getting started

### setting up

1. download [all files](https://github.com/sayo-melu/jekyll-podcast/archive/master.zip) from github.
2. copy `podcast.xml` to `[jekyll project]/`.
3. copy `podcast.html` to `[jekyll project]/_layouts/`.
4. add configs below to `[jekyll project]/_config.yaml` (⚠ before the "Build settings" section), then edit it according to your information. (see [sample](sample/_config.yaml))

``` yaml
podcast:
  title: [title]
  description: [description]
  url: /podcast.xml # podcast xml url
  author: [podcast author]
  email: [podcast email]
  logo: [podcast logo url] # logo in 1400 – 3000 pixel
  language: [language] # http://www.loc.gov/standards/iso639-2/php/code_list.php
  category: [category] # https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12
  subcategory: [subcategory]
  type: [podcast type] # episodic | serial
  explicit: [explicit state] # true | false
  complete: [complete state] # 'yes' | 'no'
  block: [block state] # 'yes' | 'no'
```

### post

1. learn kekyll with [step by step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/).
2. [create a new post](https://jekyllrb.com/docs/posts/#creating-posts) with [front matter](https://jekyllrb.com/docs/front-matter/) below, then edit it according to your information. (see [sample](/sample/2019-4-6-jekyll-podcast-sample.md))

``` yaml
---
layout: podcast
categories: podcast # podcast
title: jekyll podcast sample
author: sayo melu
season: 2
episode: 9
episodeType: full # full | trailer | bonus
explicit: false # true | false
audio: https://sample.net/audio.opus
length: 3927 # in seconds
---
```

1. write your **episode notes** below.
2. upload all jekyll project files to your server.
3. your podcast feed will be at `[jekyll project url]/podcast.xml`.

### validating

use [podcast validator](https://podba.se/validate) (web), [itunes](https://www.apple.com/itunes/) (macos, windows), [antennapod](http://antennapod.org) (android), apple podcasts (ios), etc. to validate your rss feed.

if you have any problems, please [create an issue](https://github.com/sayo-melu/jekyll-podcast/issues/new) on github to ask questions or suggest ideas.

## sample

[sayo cast](https://sayo-melu.xyz/podcast) hosted on gitlab.

## reference

- [a podcaster’s guide to rss - apple](https://help.apple.com/itc/podcasts_connect/#/itcb54353390)

- [apple ppdcasts categories - apple](https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12)

- [add a podcast using an rss feed - google](https://support.google.com/googleplay/podcasts/answer/6260341)
