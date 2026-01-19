---
layout: default
title: News
---

# News

<div class="content-wrapper">

{% for post in site.posts %}
  <article class="news-item" style="margin-bottom: 3rem;">
    <h2 style="color: #5A9FD4; margin-bottom: 0.5rem;">{{ post.title }}</h2>
    <p style="color: #666; font-size: 0.95rem; margin-bottom: 1rem;">
      <strong>{{ post.date | date: "%B %d, %Y" }}</strong>
    </p>

    {{ post.content }}

    {% unless forloop.last %}
    <div style="text-align: center; margin: 3rem 0;">
      <div style="display: inline-block; width: 100px; height: 3px; background: linear-gradient(to right, #FFB3D9, #D4BBFF); border-radius: 2px;"></div>
    </div>
    {% endunless %}
  </article>
{% endfor %}

<h2 style="margin-top: 3rem;">Recent Publications</h2>

<p>Check out our latest research on the <a href="{{ site.baseurl }}/publications/">Publications</a> page.</p>

</div>
