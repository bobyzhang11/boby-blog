---
layout: default
title: 闪念
permalink: /thoughts/
---

<h2 class="text-4xl font-bold mb-2">闪念</h2>
<p class="text-gray-500 mb-10">短思考，随时记录</p>

{% assign sorted_thoughts = site.thoughts | sort: "date" | reverse %}
{% if sorted_thoughts.size > 0 %}
<div class="space-y-6">
  {% for thought in sorted_thoughts %}
  <div class="bg-white rounded-2xl p-6 shadow-sm card-hover">
    <p class="text-lg leading-relaxed">{{ thought.content }}</p>
    <span class="text-xs text-gray-400 mt-3 block">{{ thought.date | date: "%Y-%m-%d" }}</span>
  </div>
  {% endfor %}
</div>
{% else %}
<p class="text-gray-400">暂无想法。</p>
{% endif %}
