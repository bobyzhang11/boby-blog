---
layout: default
title: 文章
permalink: /blog/
---

<h2 class="text-4xl font-bold mb-2">文章</h2>
<p class="text-gray-500 mb-10">深度阅读与分享</p>

{% if site.posts.size > 0 %}
<div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
  {% for post in site.posts %}
  <div class="bg-white rounded-2xl p-6 shadow-sm card-hover flex flex-col">
    <span class="text-xs text-gray-400">{{ post.date | date: "%Y-%m-%d" }}</span>
    <h3 class="text-lg font-semibold mt-2 mb-2">{{ post.title }}</h3>
    <p class="text-gray-500 text-sm flex-1">{{ post.excerpt | strip_html | truncate: 80 }}</p>
    <a href="{{ post.url }}" class="text-primary text-sm font-medium mt-4">阅读全文</a>
  </div>
  {% endfor %}
</div>
{% else %}
<p class="text-gray-400">暂无文章。</p>
{% endif %}
