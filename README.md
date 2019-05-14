# Jekyll Podcast

Jekyll Podcast generates audio podcast feed and note for Jekyll.

## Why Jekyll Podcast

Uploading podcasts is not as easy as uploading videos, you have to own or borrow a web server to host your content.

There are a lot of platforms for people to upload podcasts, but some of them spend your money, some of them cannot be configured to your requirement.

Although there are also some podcast holding solutions for Jekyll, they are difficult to use. And they don't have a solution to generate web pages for your podcast.

To solve these problems, I build this configurable jekyll-podcast. You can host it on [GitHub](http://github.com) for free, then you can buy you a better 🎙 microphone.

## Getting Started

### Setting Up

1. Download [all files](https://github.com/sayomelu/jekyll-podcast/archive/master.zip) from GitHub.
2. Copy `podcast.xml` to your Jekyll root `/`.
3. Copy `/_layouts/podcast.html` to `/_layouts/`.
4. Add configs below to Jekyll `/_config.yaml`, then edit it according to your information.

    ``` yaml
    podcast:
      title: [Title]
      description: [Description]
      url: /podcast.xml
      author: [Author]
      email: [Email]
      logo: [Podcast Logo URL] # Podcast logo URL, 1400 – 3000 pixels
      lang: [Language] # http://www.loc.gov/standards/iso639-2/php/code_list.php
      category: [Category] # https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12
      subcategory: [Subcategory]
      explicit: [Explicit State] # true or false
      complete: [Complete State] # yes or no
    ```

### Post

1. Create a post with front matter below, then edit it according to your information.

   ``` yaml
    ---
    layout: podcast # Must be "podcast"
    categories: podcast # Must be "podcast" or "Podcast"
    title: [Podcast Title]
    author: [Author] # Podcast author
    season: [Season Number]
    episode: [Episode Number]
    episodeType: [Episode Type] # full, trailer or bonus
    explicit: [Explicit State] # true or false
    audio: [Audio File URL]
    length: [Audio Length] # Audio length in seconds
    ---
   ```

2. Write your Episode Notes with `Markdown` below.
3. Upload it to your Jekyll server.
4. Your podcast feed will be at `[Blog URL]/podcast.xml`.

### Validating

Use [Podcast Validator](https://podba.se/validate) to validate your podcast feed.

You can also use [iTunes](https://www.apple.com/itunes/) (PC), [AntennaPod](http://antennapod.org) (Android), Apple Podcasts (iOS) to validate.

### Attention

- Your `url` in `_config.yaml` should start with `http://` or `https://`.
- Change `podcast.url` if you renamed or moved `podcast.xml`.

## Sample

[Sayo Cast](https://sayo-melu.github.io/podcast.xml) with [Sayo's Blog](http://sayo-melu.github.io) hosted on GitHub.

## Reference

[RSS feed sample](https://help.apple.com/itc/podcasts_connect/#/itcbaf351599)

[Add a podcast using an RSS feed](https://support.google.com/googleplay/podcasts/answer/6260341)

[Apple Podcasts categories](https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12)