# jekyll-podcast

jekyll-podcast generates audio podcast feed for Jekyll.

## Why do I build jekyll-podcast?

Uploading podcasts is not as easy as uploading videos, you have to own or borrow a web server to host your content.

There are a lot of platforms for people to upload podcasts, but some of them spend your money, some of them cannot be configured to your requirement.

Although there are also some podcast holding solutions for Jekyll, they are difficult to use. And they don't have a solution to generate web pages for your podcast.

To solve these problems, I build this configurable jekyll-podcast. You can host it on [GitHub](http://github.com) for free, so you can buy you a better 🎙 microphone.

## How to use?

### Setup

1. Download [all files](https://github.com/sayomelu/jekyll-podcast/archive/master.zip) from GitHub.
2. Copy `podcast.xml` to your Jekyll root `/`.
3. Duplicate `/_layouts/post.html`, and rename it to `/_layouts/podcast.html`.
4. Copy codes below to your Jekyll `/_layouts/podcast.html` before `{{ content }}`.

    ``` html
    <br><br>
    <audio controls preload="auto">
      <source src="{{ page.audio | absolute_url }}" type="{{ post.type }}">
    </audio>
    <br>
    ```

    Example

    ``` html
    ---
    layout: default
    ---

    <article class="post">

      <h1>{{ page.title }}</h1>

      <time>
          {{ page.date | date: "%Y.%m.%d" }}
      </time>

      <div class="label">
          {% for tag in page.tags %}
          <a href="/tag#{{ tag }}">
              {{ tag }}
          </a>
          {% endfor %}
      </div>
      
      <br><br>
      <audio controls preload="auto">
          <source src="{{ page.audio | absolute_url }}" type="{{ post.type }}">
      </audio>
      <br>

      {{ content }}

      {% include comment.html %}

    </article>
    ```

5. Add configs below to Jekyll `/_config.yaml`, then edit it according to your information.

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

### Post

1. Create a post with head below.
   ``` yaml
   ---
   layout: podcast
   title: Your Title
   categories: podcast
   audio: your audio address # in /url/audio.file
   type: your type # audio/x-m4a, audio/mpeg
   length: your length # audio length in seconds
   explicit: false # true or false
   ---
   ```
2. Edit post head according to your information.
3. Write your show notes with `Markdown` below.
4. Upload it to your Jekyll server.
5. Your podcast feed will be at `url/podcast.xml`.

### Validate

Use [Podcast Validator](https://podba.se/validate) to validate your podcast feed.

You can also use [AntennaPod](http://antennapod.org) to test performance on Android.

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