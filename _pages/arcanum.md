---
layout: default
title: Arcanum Caedis
permalink: /arcanum/
---

<section class="arcanum-section">
  <header class="arcanum-header">
    <h1>Crónicas de Arcanum Caedis</h1>
    <p class="intro">Sigue las últimas noticias, descubrimientos y acontecimientos místicos del plano desgarrado por la magia y la arrogancia tecnocrática.</p>
  </header>

  <div class="arcanum-posts">
    {% assign arcanum_posts = site.categories.arcanum | sort: 'date' | reverse %}
    {% for post in arcanum_posts %}
      <article class="arcanum-post">
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p class="post-date">{{ post.date | date: "%d %B %Y" }}</p>
        <p>{{ post.excerpt }}</p>
        <a href="{{ post.url }}" class="read-more">Leer más</a>
      </article>
    {% endfor %}
  </div>
</section>
