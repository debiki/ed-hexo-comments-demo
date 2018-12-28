---
title: Demo and installation instructions
discussion_id: demo-and-inst-instrs
date:   2018-01-04 0:02:00 +0000
---

Talkyard is a commenting system for Hexo and other static site generators. It's [open source](https://github.com/debiki/ed-server/); you can install it for free on your server. There's [serverless hosting](https://www.talkyard.io/plans) — no ads, no tracking, free for low traffic blogs.

This website is a static Hexo blog, with Talkyard comments — look at the bottom of the pages. Talkyard is forum software too, with chat and question-answers features: you can create a community for your website, integrated with the blog comments.

Demo video:

<iframe src="https://player.vimeo.com/video/249611399" width="684" height="385" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<!-- <a href="/2018/01/03/kindest-species/">Here's a demo Hexo discussion.</a> -->

<a href="https://www.kajmagnus.blog/new-embedded-comments">Demo discussion</a> (the one in the video).


## Quick test if this is for you

Two steps for trying out Talkyard, without signing up or getting a server:

1. Add this to your `_config.yml` file:

   ```
   talkyard_server_url: https://comments-demo.talkyard.io
   ```

2. Do real installation step 3 (three) below, i.e. add the html for the comments.

Now, regenerate your blog and look at the comment section that should appear below the blog posts. You can post test comments **but** they'll disappear later on some day.

Help forum: <https://www.talkyard.io/forum/latest/support>.


If you like it, then do real installation step 1 below, and step 2 again — and this time, specify the address to your own Talkyard comments site. (Skip step 3, you've done it already.)


## Real installation

Install this commenting system in three steps:

1. Go to <https://www.talkyard.io/plans> and choose Blog Comments. Type the address to your blog. Copy the address to your new embedded comments site.

2. In your Hexo site configuration, i.e. `_config.yml`, add this config value and paste the address:

   ```
   talkyard_server_url: https://comments-for-your-site.talkyard.net
   ```

3. Add this where you want the comments to appear:
   ```
   TEST001

   <% if (!index && post.comments && config.talkyard_server_url){ %>
   <section id="comments">
   <script>talkyardServerUrl='<%= config.talkyard_server_url %>';</script>
   <script async defer src="<%= config.talkyard_script_url || 'https://c1.ty-cdn.net/-/talkyard-comments.min.js' %>"></script>
   <div class="talkyard-comments" data-discussion-id="<%= post.discussion_id %>" style="margin-top: 45px;">
   <noscript>Please enable Javascript to view comments.</noscript>
   <p style="margin-top: 25px; opacity: 0.9; font-size: 96%">Comments powered by
   <a href="https://www.talkyard.io">Talkyard</a>.</p>
   </div>
   </section>
   <% } %>
   ```

   For this blog, I placed it at the bottom of the file `themes/landscape/layout/_partial/article.ejs`.

   Restart Hexo, reload the page in the browser. Do you see a comments section now? If so, remove `TEST001`. If not — do you see `TEST001`? If you *do* see `TEST001` but not the comments, then ask for help, see below. If you don't see `TEST001`, you added the comments code at the wrong place, or you're looking at the wrong page.

4. Optionally, add a frontmatter `discussion_id: per-discussion-id` to your blog posts / articles.
   Then, you can change the URL to your posts, without the embedded discussion disappearing.

You can ask for help in [the support forum][support-cat].


[support-cat]: https://www.talkyard.io/forum/latest/support

