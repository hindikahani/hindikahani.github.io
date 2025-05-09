---
layout: blog
title: होम
---

<section class="hero">
  <h1>हिंदी कहानियाँ</h1>
  <p>प्रेरणादायक, ऐतिहासिक और लोकप्रिय कहानियों का संग्रह।</p>
</section>

<section class="latest-stories">
  <h2 class="section-title">नवीनतम कहानियाँ</h2>
  <div class="story-grid">
    {% for post in site.posts limit:6 %}
      <div class="story-card">
        <a href="{{ post.url | relative_url }}">
          <h3>{{ post.title }}</h3>
          <p class="story-meta">{{ post.date | date: "%B %d, %Y" }}</p>
          {% if post.excerpt %}
            <p>{{ post.excerpt | truncatewords: 20 }}...</p>
          {% endif %}
        </a>
      </div>
    {% endfor %}
  </div>
  {% if site.posts.size > 6 %}
    <div class="view-all">
      <a href="/blog/">सभी कहानियाँ देखें</a>
    </div>
  {% endif %}
</section>

<section class="popular-stories">
  <h2 class="section-title">लोकप्रिय कहानियाँ</h2>
  <div class="story-grid">
    {% assign popular_posts = site.posts | where: "popular", true %}
    {% if popular_posts.size > 0 %}
      {% for post in popular_posts limit:3 %}
        <div class="story-card popular">
          <a href="{{ post.url | relative_url }}">
            <h3>{{ post.title }}</h3>
            {% if post.excerpt %}
              <p>{{ post.excerpt | truncatewords: 15 }}...</p>
            {% endif %}
          </a>
        </div>
      {% endfor %}
    {% else %}
      <p>अभी कोई लोकप्रिय कहानियाँ उपलब्ध नहीं हैं।</p>
    {% endif %}
  </div>
  {% if popular_posts.size > 3 %}
    <div class="view-all">
    </div>
  {% endif %}
</section>
