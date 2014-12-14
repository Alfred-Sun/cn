---
layout: home
title: 主页 - Alfred Sun
tagline: 为梦想而战！
group: navigation
weight: 0
---
{% include JB/setup %}

{% if site.posts.size < 8 %}
{% capture post_num %}{{ site.posts.size | minus: 1 }}{% endcapture %}
{% else %}
{% assign post_num = 7 %}
{% endif %}

{% for i in (0..post_num) %}
{% assign post = site.posts[i] %}
  <article>
    <h2><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h2>
    <div class="details">
      <p>{{ post.date | date_to_long_string }}</p>
    </div>
    <p class="summary">
    {% if post.description %}{{ post.description  | strip_html | strip_newlines}}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 200 }}{% endif %}
    <a href="{{ BASE_PATH }}{{ post.url }}">阅读全文...</a></p>
  </article>
{% endfor %}

<p><a href="{{ BASE_PATH }}{{ site.JB.archive_path }}">所有文章列表&#8594;</a></p>

