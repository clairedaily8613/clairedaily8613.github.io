---
layout: default
title: 旅途紀錄 — Claire Daily
permalink: /archive/
---

<div class="container">
  <div class="archive-header">
    <h1>旅途紀錄</h1>
    <p>每週一篇，記下這段在英國重新開始的日子。</p>
  </div>

  {% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
  {% for year_group in posts_by_year %}
  <div class="year-group">
    <div class="year-label">{{ year_group.name }}</div>
    <div class="post-list">
      {% for post in year_group.items %}
      <a href="{{ post.url }}" class="post-list-item">
        <div class="post-list-left">
          <div class="post-list-title">{{ post.title }}</div>
          <div class="post-list-excerpt">{{ post.content | strip_html | truncatewords: 12 }}</div>
        </div>
        <span class="post-list-date">{{ post.date | date: "%-m/%-d" }}</span>
      </a>
      {% endfor %}
    </div>
  </div>
  {% endfor %}
</div>
