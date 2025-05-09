---
layout: blog
title: होम
---

<section class="latest-posts">
  <h2 class="section-title">नवीनतम कहानियाँ</h2>
  <div class="post-list">
    {% for post in site.posts limit:5 %}
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    {% endfor %}
    {% if site.posts.size > 5 %}
      <div class="view-all">
        <a href="/blog/">सभी नवीनतम कहानियाँ देखें</a>
      </div>
    {% endif %}
  </div>
</section>

<section class="popular-posts">
  <h2 class="section-title">लोकप्रिय कहानियाँ</h2>
  <div class="post-list">
    {% assign popular_posts = site.posts | where: "popular", true %}
    {% for post in popular_posts limit:3 %}
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    {% endfor %}
    {% if popular_posts.size > 3 %}
      <div class="view-all">
        </div>
    {% endif %}
    {% if popular_posts.size == 0 %}
      <p>अभी कोई लोकप्रिय कहानियाँ उपलब्ध नहीं हैं।</p>
    {% endif %}
  </div>
</section>
