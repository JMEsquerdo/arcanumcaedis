---
header_type: "hero"
header_img : "assets/img/Arcanum.webp"
title: Arcanum Caedis
permalink: /arcanum/
---

<section class="arcanum-section">
  <header class="arcanum-header">
    <h1>Crónicas de Arcanum Caedis</h1>
    <p>Sigue las últimas noticias, descubrimientos y acontecimientos místicos del plano desgarrado por la magia y la arrogancia tecnocrática.</p>
  </header>

  <div id="arcanum-posts" class="row g-3">
    {% assign arcanum_posts = site.categories.arcanum | sort: 'date' | reverse %}
    {% for post in arcanum_posts %}
      <div class="post-item col-12 col-md-6" style="display: none;">
        <div class="card chulapa-card shadow-sm h-100">
          <div class="row g-0">
            {% if post.image %}
            <div class="col-4 d-none d-md-block">
              <img src="{{ post.image | relative_url }}" class="img-fluid rounded-start" alt="{{ post.title }}">
            </div>
            {% endif %}
            <div class="col">
              <div class="card-body">
                <h2 class="card-title h5"><a href="{{ post.url }}">{{ post.title }}</a></h2>
                <p class="card-text"><small class="text-muted">{{ post.date | date: "%d %B %Y" }}</small></p>
                <p class="card-text">{{ post.excerpt }}</p>
                <a href="{{ post.url }}" class="btn btn-sm btn-outline-secondary">Leer más</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>

  <!-- Controles de paginación -->
  <nav class="pagination-nav mt-4 text-center">
    <ul id="pagination" class="pagination justify-content-center"></ul>
  </nav>
</section>


