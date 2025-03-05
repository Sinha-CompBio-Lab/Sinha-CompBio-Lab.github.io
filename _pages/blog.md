---
layout: archive
title: "Blog"
permalink: /blog/
author_profile: true
---

<style>
  .blog-list {
    margin-bottom: 40px;
  }
  
  .blog-entry {
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    padding: 25px;
    margin-bottom: 25px;
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  }
  
  .blog-meta {
    font-size: 0.9em;
    color: #666;
    margin-bottom: 15px;
  }
  
  .blog-title {
    margin-top: 0;
    margin-bottom: 15px;
  }
  
  .blog-excerpt {
    margin-bottom: 15px;
  }
  
  .read-more {
    display: inline-block;
    padding: 6px 12px;
    background-color: #0066cc;
    color: white;
    text-decoration: none;
    border-radius: 4px;
    font-weight: 500;
  }
  
  .read-more:hover {
    background-color: #0055aa;
  }
</style>

<div class="blog-list">
  {% for post in site.posts %}
    <div class="blog-entry">
      <div class="blog-meta">{{ post.date | date: "%B %d, %Y" }}{% if post.categories %} • {{ post.categories | join: ", " }}{% endif %}</div>
      <h2 class="blog-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <div class="blog-excerpt">
        {% if post.excerpt %}
          {{ post.excerpt | markdownify }}
        {% endif %}
      </div>
      <a href="{{ post.url | relative_url }}" class="read-more">Read More</a>
    </div>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
  <p>No blog posts found. Check back soon!</p>
{% endif %}
