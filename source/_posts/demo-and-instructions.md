---
title: Demo and installation instructions
discussion_id: demo-and-inst-instrs
date:   2018-01-04 0:02:00 +0000
---

Talkyard is a new commenting system for Hexo and other static site generators. It's [open source](https://github.com/debiki/ed-server/) so you can install it for free on your own server. There's hosting too, if you don't want to maintain your own server. No ads, no tracking. Lightweight, just 140 kb javascript (in comparison to Disqus' about 750 kb).

This website is a static Hexo blog, with Talkyard comments below each blog post — look at the bottom of the pages. Talkyard is forum software too, with chat and Q&A features — so you can create a community for your website, integrated with the blog comments.

Demo video:

<iframe src="https://player.vimeo.com/video/249611399" width="684" height="385" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<a href="/2018/01/03/kindest-species/">Here's a demo Hexo discussion.</a>

<a href="https://www.kajmagnus.blog/new-embedded-comments">Longer demo discussion (the one in the video).</a>


## Quick test if this is for you

Maybe you don't want to get a server and install, or sign up for our hosted service, just to find out if Talkyard works for your blog / website? Here're two quick steps for you to try out Talkyard:

1. Add this to your `_config.yml` file:

   ```
   talkyard_comments_server_url: https://comments.demo.talkyard.io
   ```

2. Do real installation step 3 (three) below, i.e. add the html for the comments.

Now, regenerate your blog and look at the comment section that should appear below the blog posts. You can post test comments **but** they'll disappear later on some day. Currently the comment section background color is always white, but later on you'll be able to tweak how it looks.

Are you satisfied with how it looks? If not, please tell us/me: <https://www.talkyard.io/forum/latest/support>.


If you like it, then do real installation step 1 below, and step 2 again — and this time, specify the address to your own Talkyard site. (Skip step 3, you've done it already.)


## Real installation

Install this commenting system in three steps:

1. Go to <https://www.talkyard.io> and click Create Community, choose Blog Comments and type your website address. Copy the address to your new embedded comments site.

2. In your Hexo site configuration, i.e. `_config.yml`, add this config value and paste the address:

   ```
   talkyard_comments_server_url: https://comments-for-your-site.talkyard.io
   ```

3. Add this where you want the comments to appear:
   ```
   TEST001

   <% if (!index && post.comments && config.talkyard_comments_server_url){ %>
   <section id="comments">
   <script>talkyardCommentsServerUrl='<%= config.talkyard_comments_server_url %>';</script>
   <script async defer src="<%= config.talkyard_comments_script_url || 'https://cdn.talkyard.io/-/talkyard-comments.min.js' %>"></script>
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

Again, note that Talkyard also is forum software, with chat and Q&A features — so you can create a community for your website, integrated with the blog comments.

You can ask for help in [the support forum][support-cat], and [suggest ideas here][ideas-cat]. Or post a comment below on this page (test comments are fine too).


[support-cat]: https://www.talkyard.io/forum/latest/support
[ideas-cat]: https://www.talkyard.io/forum/latest/ideas

