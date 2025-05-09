---
layout: blog
title: होम
---

<section>
  <h2 class="section-title">नवीनतम कहानियाँ</h2>
  <div class="post-list">
    {% for post in site.posts limit:5 %}
      <div class="post-item">
        <a href="{{ post.url | relative_url }}">
          <h3>{{ post.title }}</h3>
        </a>
        <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
        {% if post.excerpt %}
          <p>{{ post.excerpt | truncatewords: 20 }}</p>
        {% endif %}
      </div>
    {% endfor %}
    {% if site.posts.size > 5 %}
      <a href="/blog/">और पुरानी कहानियाँ देखें</a>
    {% endif %}
  </div>
</section>

<section>
  <h2 class="section-title">लोकप्रिय कहानियाँ</h2>
  <div class="post-list">
    {% assign popular_posts = site.posts | where: "popular", true %}
    {% for post in popular_posts limit:5 %}
      <div class="post-item">
        <a href="{{ post.url | relative_url }}">
          <h3>{{ post.title }}</h3>
        </a>
        {% if post.excerpt %}
          <p>{{ post.excerpt | truncatewords: 20 }}</p>
        {% endif %}
      </div>
    {% empty %}
      <p>अभी कोई लोकप्रिय कहानियाँ नहीं हैं।</p>
    {% endfor %}
  </div>
</section>
