---
layout: page
title: Docs
---

<section class="c-archives">
<ul class="c-archives__list">
  {% for post in site.posts  %}
    <li class="c-archives__item">
      <h3>
        <a href="{{ post.url | prepend: site.baseurl }}">{{post.title}}</a>
        <br />
        <small>{{post.description}}</small>
      </h3>
    </li>
  {% endfor %}
</ul>
</section>
