---
title: Browse Authors
layout: page
permalink: /authors.html
---

<h2 id="browse-authors" class="mb-4">Browse Authors</h2>

<div class="row row-cols-1 row-cols-sm-2 row-cols-md-4 row-cols-lg-5 g-4 mb-4">
    {% comment %} Loop through every author in author.csv {% endcomment %}
    {% for author in site.data.author %}
    <div class="col">
        <div class="card h-100 shadow-sm">
            
            {% comment %} 1. Author Photo (Constructed dynamically from ID) {% endcomment %}
            <a href="{{ '/authors/' | append: author.id | append: '.html' | relative_url }}">
                <img src="{{ '/objects/small/' | append: author.id | append: '_sm.jpg' | relative_url }}" class="card-img-top p-2" alt="{{ author.given-names }} {{ author.family-names }}" style="object-fit: cover; object-position: top; height: 300px; border-radius: 12px;" onerror="this.style.display='none'">
            </a>
            
            <div class="card-body">
                {% comment %} 2. Author Name {% endcomment %}
                <h5 class="card-title text-center mb-3">
                    <a href="{{ '/authors/' | append: author.id | append: '.html' | relative_url }}" class="text-dark text-decoration-none fw-bold">
                        {{ author.given-names }} {{ author.family-names }}
                    </a>
                </h5>

                {% comment %} 3. Novels Buttons {% endcomment %}
                {% assign author_novels = site.data.novel | where: "author_id", author.id %}
                {% if author_novels.size > 0 %}
                <div class="mb-3 text-center">
                    <p class="card-text mb-2" style="font-size: 0.9em;"><strong>Novels:</strong><br>
                    {% for novel in author_novels %}
                    <a href="{{ '/items/' | append: novel.objectid | append: '.html' | relative_url }}" class="btn btn-sm btn-outline-primary m-1 text-wrap" style="font-size: 0.8em;">{{ novel.title }}</a>
                    {% endfor %}
                    </p>
                </div>
                {% endif %}

                {% comment %} 4. Religions with Significance Badges {% endcomment %}
                {% assign rel_rows = site.data.author_religion | where: "author_id", author.id %}
                {% if rel_rows.size > 0 %}
                <p class="card-text mb-2" style="font-size: 0.9em;">
                    <strong>Religions:</strong><br>
                    {% for r in rel_rows %}
                        {% comment %} Look up the religion name from religion.csv {% endcomment %}
                        {% assign rel_rec = site.data.religion | where: "id", r.religion_id | first %}
                        {% if rel_rec %}
                        <span class="d-inline-block mb-1">
                            {{ rel_rec.religion }}
                            {% if r.significance and r.significance != "" %}
                                {% if r.significance == 'major' %}
                                    {% assign badge_class = 'bg-primary text-white' %}
                                {% else %}
                                    {% assign badge_class = 'bg-light text-dark border' %}
                                {% endif %}
                                <span class="badge {{ badge_class }}" style="font-size: 0.75em; vertical-align: middle;">{{ r.significance }}</span>
                            {% endif %}
                        </span><br>
                        {% endif %}
                    {% endfor %}
                </p>
                {% endif %}

                {% comment %} 5. Locations with Significance Badges {% endcomment %}
                {% assign loc_rows = site.data.author_country | where: "author_id", author.id %}
                {% if loc_rows.size > 0 %}
                <p class="card-text mb-2" style="font-size: 0.9em;">
                    <strong>Locations:</strong><br>
                    {% for c in loc_rows %}
                        {% assign country_rec = site.data.country | where: "alpha-3-code", c.country_id | first %}
                        {% if country_rec %}
                        <span class="d-inline-block mb-1">
                            {{ country_rec.country }}
                            {% if c.significance and c.significance != "" %}
                                {% if c.significance == 'major' %}
                                    {% assign badge_class = 'bg-primary text-white' %}
                                {% else %}
                                    {% assign badge_class = 'bg-light text-dark border' %}
                                {% endif %}
                                <span class="badge {{ badge_class }}" style="font-size: 0.75em; vertical-align: middle;">{{ c.significance }}</span>
                            {% endif %}
                        </span><br>
                        {% endif %}
                    {% endfor %}
                </p>
                {% endif %}
                
            </div>
        </div>
    </div>
    {% endfor %}
</div>