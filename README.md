# jekyll-podcast

jekyll-podcast generates audio podcast feed for Jekyll.

## Why do I build jekyll-podcast?

Uploading podcasts is not as easy as uploading videos, you have to own or borrow a web server to host your content.

There are a lot of platforms for people to upload podcasts, but some of them spend you money, some of them can not be configured to your requirement.

Although there are also some podcast holding solutions for jekyll, they are difficult to use. And they don't have a solution to generate web pages for your podcast.

To solve these problem, I build this configurable jekyll-podcast. You can host it on [GitHub](http://github.com) for free, so you can buy you a better 🎙 microphone.

## How to use?

### Setup

1. Download [all files](https://github.com/sayomelu/jekyll-podcast/archive/master.zip) from GitHub.
2. Copy `podcast.xml` to your Jekyll `root`.
3. Copy `_layouts/podcast.html` to your Jekyll `_layouts/`
4. Add configs below to Jekyll `_config.yaml`.

    ``` yaml
    podcast:
        title: My Title
        description: My description
        url: /podcast.xml
        author: My Author
        email: My Email
        logo: /my-logo.png # URL of your podcast logo or avatar, 1400 – 3000 pixels better
        lang: en_US # language_TERRITORY
        
        # Follow https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12
        category1: My Category1
        subcategory1: My Subcategory1
        category2: My Category1
        subcategory2: My Subcategory2

        explicit: false # true or false
        complete: no # yes or no
    ```

### Config

1. Edit your `_config.yaml` according to your infomation.
2. Edit `_layouts/podcast.html` to fit your `_layouts/post.html` style.

### Post

1. Create a post with head below.
   ``` yaml
   ---
   layout: podcast
   title: Your Title
   categories: podcast
   type: audio/mpeg # audio/x-m4a, audio/mpeg
   audio: your audio address
   length: your length length # audio length in seconds
   explicit: false # true or false
   ---
   ```
2. Edit post head according to your infomation.
3. Write your show notes below.
4. Upload it to your Jekyll server.
5. Your podcast feed will be at `yoururl/podcast.xml`.

### Validate

Use [http://podba.se/validate/](https://podba.se/validate) to validate your podcast feed.

You can also use [AntennaPod](http://antennapod.org) to test performance on Android.

## Attention

- Your `site.url` should start with `http://` or `https://`.
- Change `url` if you renamed or moved `podcast.xml`.
- `category`, `subcategory` don't need to be all filled.

## Sample

My [podcast](https://sayomelu.github.io/podcast.xml) on my [blog](http://sayomelu.github.io) hosted on GitHub.

## Reference

[RSS feed sample](https://help.apple.com/itc/podcasts_connect/#/itcbaf351599)

[Add a podcast using an RSS feed](https://support.google.com/googleplay/podcasts/answer/6260341)

[Apple Podcasts categories](https://help.apple.com/itc/podcasts_connect/#/itc9267a2f12)