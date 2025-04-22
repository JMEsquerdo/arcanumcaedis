---
header_type: "hero"
header_img : "assets/img/tierra.webp"
title: La Tierra
permalink: /tierra/
---

<section class="tierra-section">
  <header class="tierra-header text-center">
    <h1>Noticias de tierra</h1>
    <p>Sigue las últimas noticias, descubrimientos y acontecimientos mágicos del plano.</p>
  </header>

  <div id="tierra-posts" class="row g-3">
    {% assign tierra_posts = site.categories.tierra | sort: 'date' | reverse %}
    {% for post in tierra_posts %}
      <div class="post-item col-12 col-md-6" style="display: none;">
        <div class="card chulapa-card tierra shadow-sm h-100">
          <div class="row g-0">
            {% if post.image %}
              <div class="col-4 d-none d-md-block">
                <img src="{{ post.image | relative_url }}" class="img-fluid rounded-start" alt="{{ post.title }}">
              </div>
            {% endif %}
            <div class="col">
              <div class="card-body d-flex flex-column">
                <!-- Contenido superior: título y fecha -->
                <div>
                  <h2 class="card-title h5 text-center">
                    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
                  </h2>
                  <p class="card-text text-center">
                    <small class="text-muted">{{ post.date | date: "%d %B %Y" }}</small>
                  </p>
                </div>
                <!-- Extracto con espacio flexible -->
                <div class="flex-grow-1 mt-2">
                  <p class="card-text">{{ post.excerpt }}</p>
                </div>
                <!-- Botón "Leer más" abajo -->
                <div class="mt-3">
                  <a href="{{ post.url | relative_url }}" class="btn btn-sm btn-outline-secondary">Leer más</a>
                </div>
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





