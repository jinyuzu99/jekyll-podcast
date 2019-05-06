# jekyll-podcast

jekyll-podcast generates audio podcast feed and note for Jekyll.

## Why jekyll-podcast

Uploading podcasts is not as easy as uploading videos, you have to own or borrow a web server to host your content.

There are a lot of platforms for people to upload podcasts, but some of them spend your money, some of them cannot be configured to your requirement.

Although there are also some podcast holding solutions for Jekyll, they are difficult to use. And they don't have a solution to generate web pages for your podcast.

To solve these problems, I build this configurable jekyll-podcast. You can host it on [GitHub](http://github.com) for free, so you can buy you a better 🎙 microphone.

## Getting Started

### Seting Up

1. Download [all files](https://github.com/sayomelu/jekyll-podcast/archive/master.zip) from GitHub.
2. Copy `podcast.xml` to your Jekyll root `/`.
3. Copy `/_layouts/podcast.html` to `/_layouts/`.
4. Add configs below to Jekyll `/_config.yaml`, then edit it according to your information.

    ``` yaml
    podcast:
    title: [Title]
    description: [description]
    url: /podcast.xml
    author: [Author]
    email: [email]
    logo: [/my-logo.png] # URL of your podcast logo or avatar, 1400 – 3000 pixels better
    lang: en # http://www.loc.gov/standards/iso639-2/php/code_list.php
    category: My Category1 # https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12
    subcategory: My Subcategory1
    explicit: false # true or false
    complete: no # yes or no
    ```

### Post

1. Create a post with front matter below, then edit it according to your information.

   ``` yaml
    ---
    layout: podcast
    categories: podcast
    title: [Podcast Title]
    author: [author] # podcast author
    season: [season-number]
    episode: [episode-number]
    episodeType: [episode-type] # full, trailer or bonus
    explicit: [explicit] # true or false
    audio: [audio-file-url]
    length: [audio-length] # audio length in seconds
    ---
   ```

2. Write your Show Notes with `Markdown` below.
3. Upload it to your Jekyll server.
4. Your podcast feed will be at `url/podcast.xml`.

### Validating

Use [Podcast Validator](https://podba.se/validate) to validate your podcast feed.

You can also use [iTunes](https://www.apple.com/itunes/) with `itpc://your.podcast.url`, [AntennaPod](http://antennapod.org) to test performance on Android.

### Attention

- Your `site.url` should start with `http://` or `https://`.
- Change `podcast.url` if you renamed or moved `podcast.xml`.
- `podcast.category`, `podcast.subcategory` don't need to be all filled.

## Sample

My [podcast](https://sayomelu.github.io/podcast.xml) on my [blog](http://sayomelu.github.io) hosted on GitHub.

## Reference

[RSS feed sample](https://help.apple.com/itc/podcasts_connect/#/itcbaf351599)

[Add a podcast using an RSS feed](https://support.google.com/googleplay/podcasts/answer/6260341)

[Apple Podcasts categories](https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12)