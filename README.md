# Jekyll Podcast

Jekyll Podcast generates audio podcast feed and note for Jekyll.

## Why Jekyll Podcast

Uploading podcasts is not as easy as uploading videos, you have to own or borrow a web server to host your content.

There are a lot of platforms for people to upload podcasts, but some of them spend your money, some of them cannot be configured to your requirement.

Although there are also some podcast holding solutions for Jekyll, they are difficult to use. And they don't have a solution to generate web pages for your podcast.

To solve these problems, I build this configurable jekyll-podcast. You can host it on free Jekyll services (like [GitHub](http://github.com)), then you can buy a better 🎙.

## Getting Started

### Setting Up

1. Download [all files](https://github.com/sayo-melu/jekyll-podcast/archive/master.zip) from GitHub.
2. Copy `podcast.xml` to `[Jekyll Project]/`.
3. Copy `podcast.html` to `[Jekyll Project]/_layouts/`.
4. Add configs below to Jekyll `[Jekyll Project]/_config.yaml`, then edit it according to your information. (see [sample](sample/_config.yaml))

``` yaml
podcast:
  title: [Title]
  description: [Description]
  url: /podcast.xml # Podcast XML URL
  author: [Podcast Author]
  email: [Podcast Email]
  logo: [Podcast Logo URL] # Logo in 1400 – 3000 pixel
  language: [Language] # http://www.loc.gov/standards/iso639-2/php/code_list.php
  category: [Category] # https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12
  subcategory: [Subcategory]
  type: [Podcast Type] # episodic | serial
  explicit: [Explicit State] # true | false
  complete: [Complete State] # "yes" | "no"
  block: [Block State] # "yes" | "no"
```

### Post

1. Learn Jekyll with [Step by Step Tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/).
2. [Create a new post](https://jekyllrb.com/docs/posts/#creating-posts) with [front matter](https://jekyllrb.com/docs/front-matter/) below, then edit it according to your information. (see [sample](/sample/2019-4-6-jekyll-podcast-sample.md))

``` yaml
---
layout: podcast
categories: podcast # podcast | Podcast
title: [Podcast Title]
author: [Episode Author]
season: [Season Number]
episode: [Episode Number]
episodeType: [Episode Type] # full | trailer | bonus
explicit: [Explicit State] # true | false
audio: [Audio File URL]
length: [Audio Length] # in seconds
---
```

1. Write your **Episode Notes** below.
2. Upload all Jekyll project files to your Jekyll server.
3. Your podcast feed will be at `[Jekyll Project URL]/podcast.xml`.

### Validating

Use [Podcast Validator](https://podba.se/validate) to validate your podcast feed.

You can also use [iTunes](https://www.apple.com/itunes/) (macOS, Windows), [AntennaPod](http://antennapod.org) (Android), Apple Podcasts (iOS) to validate.

### Attention

- Your `url` in `_config.yaml` should start with `http://` or `https://`.
- Change `podcast.url` if you renamed or moved `podcast.xml`.

## Sample

[Sayo Cast](https://sayo-melu.github.io/podcast.xml) with [Sayo's Blog](http://sayo-melu.github.io) hosted on GitHub.

## Reference

- [A podcaster’s guide to RSS - Apple](https://help.apple.com/itc/podcasts_connect/#/itcb54353390)

- [Apple Podcasts categories - Apple](https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12)

- [Add a podcast using an RSS feed - Google](https://support.google.com/googleplay/podcasts/answer/6260341)