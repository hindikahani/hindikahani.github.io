---
layout: blog
title: होम
---

<section>
  <h2 class="section-title">नई कहानियाँ</h2>
  <div class="post-list">
    {% for post in site.posts %}
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    {% endfor %}
  </div>
</section>

<section>
  <h2 class="section-title">लोकप्रिय कहानियाँ</h2>
  <div class="post-list">
    {% for item in site.data.popular %}
      <a href="{{ item.url }}">{{ item.title }}</a>
    {% endfor %}
  </div>
</section>
