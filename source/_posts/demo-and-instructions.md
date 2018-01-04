---
title: Demo and installation instructions
discussion_id: demo-and-inst-instrs
date:   2018-01-04 0:02:00 +0000
---

This is a new commenting system for Hexo and other static site generators. It's called ed-comments (ed = Effective Discussions) and it's [open source](https://github.com/debiki/ed-server/) so you can install it for free on your own server. There's hosting too, so it's serverless. No ads, no tracking. Lightweight, just 140 kb javascript (in comparison to Disqus' about 750 kb).

This website is a static Hexo blog, with ed-comments below each blog post (at the bottom of this page).

Demo video:

<iframe src="https://player.vimeo.com/video/249611399" width="684" height="385" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


## Quick test if this is for you

Maybe you don't want to get a server and install, or sign up for our hosted service, just to find out if ed-comments works for your blog / website? Here're two quick steps for you to try out ed-comments:

1. Add this to your `_config.yml` file:

   ```
   ed_comments_server_url: https://comments.demo.ed.community
   ```

2. Do real installation step 3 below, i.e. add the html for the comments.

Now, regenerate your blog and look at the comment section that shoud now appear below the blog posts.  Are you satisfied with how it looks? If not, please tell us/me: <https://www.ed.community/forum/> :- P. Currently the comment section background color is always white, but later on you'll be able to tweak how it looks.

You can post test comments **but** they'll disappear later on some day.

If you like it, then do real-installation-step-1 below, and step 2 again, but this time, specify the address to your own ed-comments site. (Skip step 3, you've done it already.)


## Real installation

Install this commenting system in three steps:

1. Go to <https://www.ed.community> and click Create Community, choose Blog Comments and type your website address.
   Copy the address to your new embedded comments site.

2. In your Hexo site configuration, i.e. `_config.yml`, add a config value and paste the address, like so:

   ```
   ed_comments_server_url: https://comments-for-your-site.ed.community
   ```

3. Add this where you want the comments to appear:
   ```
   <% if (!index && post.comments && config.ed_comments_server_url){ %>
   <section id="comments">
   <script>edCommentsServerUrl='<%= config.ed_comments_server_url %>';</script>
   <script async defer src="https://edm-49f8.kxcdn.com/-/ed-comments.min.js"></script>
   <div class="ed-comments" data-discussion-id="<%= post.discussion_id %>" style="margin-top: 45px;">
   <noscript>Please enable Javascript to view comments.</noscript>
   <p style="margin-top: 25px; opacity: 0.9; font-size: 96%">Comments powered by
   <a href="https://www.ed.community">Effective Discussions</a>.</p>
   </div>
   </section>
   <% } %>
   ```

4. Optionally, add a frontmatter `discussion_id: per-discussion-id` to your blog posts / articles.
   Then, you can change the URL to your posts, without the embedded discussion disappearing.

You can ask for help in [the support forum][support-cat], and [suggest ideas here][ideas-cat].


[support-cat]: https://www.ed.community/forum/latest/support
[ideas-cat]: https://www.ed.community/forum/latest/ideas
