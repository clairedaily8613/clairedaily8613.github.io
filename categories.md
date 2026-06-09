---
layout: default
title: 分類 — Claire Daily
permalink: /categories/
---

<div class="container">
  <div class="archive-header">
    <h1>足跡</h1>
  </div>

  <div class="category-group">
    <h2 class="category-title">電子報</h2>
    <div class="year-list">
      {% assign years = site.posts | group_by_exp: "post", "post.date | date: '%Y'" | map: "name" | reverse %}
      {% for year in years %}
      <a href="/categories/{{ year }}/" class="year-link">{{ year }}</a>
      {% endfor %}
    </div>
  </div>
</div>
