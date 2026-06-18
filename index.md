---
layout: default
title: Claire Daily
description: Claire 踏上新的旅途——每週生活紀錄。
---

<div class="container">
  <section class="hero">
    <h1>Claire 踏上新的旅途</h1>
    <p class="hero-desc">Claire Daily 是我的每週生活紀錄。這裡有英國日常、求職進度、AI 協作、料理實驗與個人觀察，寫給正在重建生活的自己，也寫給剛好路過的你。</p>
  </section>

  {% assign latest = site.posts.first %}
  {% if latest %}
  <div class="latest-label"><span>最新一篇</span></div>
  <article class="post-card-featured">
    <div class="post-meta">
      <span class="post-date">{{ latest.date | date: "%Y 年 %-m 月 %-d 日" }}</span>
      {% if latest.week %}<span class="post-week">{{ latest.week }}</span>{% endif %}
    </div>
    <h2>{{ latest.title }}</h2>
    <p class="post-preview">{{ latest.content | strip_html | truncatewords: 20 }}</p>
    <a href="{{ latest.url }}" class="read-more">繼續閱讀 →</a>
  </article>
  {% endif %}

  <section class="social-section">
    <p class="section-title">找到我</p>
    <div class="social-grid">
      <a href="https://newsletter.clairedaily.com/landingpagef" target="_blank" class="social-link"><span class="social-dot"></span>電子報</a>
      <a href="https://www.instagram.com/clairedaily868/" target="_blank" class="social-link"><span class="social-dot"></span>Instagram</a>
      <a href="https://www.threads.com/@clairedaily868" target="_blank" class="social-link"><span class="social-dot"></span>Threads</a>
      <a href="https://www.facebook.com/ClaireDaily868" target="_blank" class="social-link"><span class="social-dot"></span>Facebook</a>
    </div>
  </section>
</div>
