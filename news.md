---
layout: default
title: News
---

# News

<div class="content-wrapper">

{% for post in site.posts %}
  <article class="news-item" style="margin-bottom: 4rem;">
    <h2 style="color: #5A9FD4; margin-bottom: 0.5rem;">{{ post.title }}</h2>
    <p style="color: #666; font-size: 0.95rem; margin-bottom: 1rem;">
      <strong>{{ post.date | date: "%B %d, %Y" }}</strong>
    </p>

    {{ post.content }}

    {% if post.image %}
    <p style="text-align: center; margin: 1.5rem 0;">
      <img src="{{ site.baseurl }}{{ post.image }}" alt="{{ post.title }}" style="max-width: 400px; width: 100%; height: auto; border-radius: 8px;">
    </p>
    {% endif %}
  </article>
{% endfor %}

<h2 style="margin-top: 3rem;">Recent Publications</h2>

<p>Check out our latest research on the <a href="{{ site.baseurl }}/publications/">Publications</a> page.</p>

</div>
