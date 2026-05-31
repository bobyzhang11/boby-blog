---
layout: default
title: 首页
---

<div class="grid md:grid-cols-2 gap-12 items-center mb-24">
  <div>
    <h1 class="text-5xl font-bold leading-tight mb-6">想法被看见<br/>知识被分享</h1>
    <p class="text-lg text-gray-500 mb-8">这里记录着我的思考、收藏的文章，以及可能有用的资料。</p>
    <a href="/blog" class="inline-block bg-primary text-white px-8 py-3 rounded-full font-medium shadow-md hover:shadow-lg">浏览文章</a>
  </div>
  <div class="bg-white rounded-2xl shadow-xl p-8 aspect-square flex items-center justify-center">
    <svg width="160" height="160" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
      <circle cx="100" cy="100" r="96" stroke="#0071e3" stroke-width="6" stroke-dasharray="12 12" opacity="0.3"/>
      <circle cx="100" cy="100" r="60" fill="#0071e3" opacity="0.1"/>
      <circle cx="100" cy="100" r="36" fill="#0071e3" opacity="0.4"/>
      <rect x="94" y="60" width="12" height="12" rx="4" fill="#0071e3"/>
      <rect x="70" y="100" width="12" height="12" rx="4" fill="#0071e3"/>
      <rect x="118" y="100" width="12" height="12" rx="4" fill="#0071e3"/>
      <rect x="94" y="128" width="12" height="12" rx="4" fill="#0071e3"/>
    </svg>
  </div>
</div>

<div class="grid md:grid-cols-2 gap-8">
  <div class="bg-white rounded-2xl p-8 shadow-sm card-hover">
    <span class="text-xs font-semibold text-primary uppercase">最新文章</span>
    {% assign latest_post = site.posts.first %}
    {% if latest_post %}
    <h3 class="text-xl font-bold mt-2">{{ latest_post.title }}</h3>
    <p class="text-gray-500 mt-2 text-sm">{{ latest_post.excerpt | strip_html | truncate: 50 }}</p>
    <a href="{{ latest_post.url }}" class="text-primary font-medium text-sm mt-4 inline-block">阅读更多 →</a>
    {% else %}
    <h3 class="text-xl font-bold mt-2">还没有文章</h3>
    <p class="text-gray-500 mt-2 text-sm">马上写第一篇吧</p>
    {% endif %}
  </div>
  <div class="bg-white rounded-2xl p-8 shadow-sm card-hover">
    <span class="text-xs font-semibold text-primary uppercase">最近想法</span>
    {% assign latest_thought = site.thoughts | sort: "date" | reverse | first %}
    {% if latest_thought %}
    <h3 class="text-xl font-bold mt-2">{{ latest_thought.title }}</h3>
    <p class="text-gray-500 mt-2 text-sm">{{ latest_thought.date | date: "%Y-%m-%d" }}</p>
    {% else %}
    <h3 class="text-xl font-bold mt-2">还没有想法</h3>
    <p class="text-gray-500 mt-2 text-sm">记录你的第一个闪念</p>
    {% endif %}
    <a href="/thoughts" class="text-primary font-medium text-sm mt-4 inline-block">查看全部想法 →</a>
  </div>
</div>
