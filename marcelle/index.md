---
layout: default
title: Movere Docere Placere
---

# Movere Docere Placere

> « Movere, docere, placere »  
> <span style="float:right;">— Horace, *Art poétique*</span>

Bienvenue sur **Movere Docere Placere**.  
Ce site est dédié à la devise d’Horace, qui résume l’ambition de toute œuvre littéraire : émouvoir, instruire, plaire.

---

## Menu des catégories

<ul>
{% assign categories = site.pages | map: "dir" | uniq | sort %}
{% for cat in categories %}
  {% assign cat_name = cat | split: '/' | last %}
  {% unless cat == "/" or cat contains "_site" or cat contains "_layouts" or cat contains "_includes" or cat contains "_sass" or cat contains "assets" or cat_name == "" or cat == page.dir %}
    <li>
      <strong>{{ cat_name | capitalize }}</strong>
      <ul>
        {% assign articles = site.pages | where: "dir", cat | sort: "title" %}
        {% for article in articles %}
          {% if article.name != "index.md" and article.name != "index.html" %}
            <li><a href="{{ article.url }}">{{ article.title | default: article.name }}</a></li>
          {% endif %}
        {% endfor %}
      </ul>
    </li>
  {% endunless %}
{% endfor %}
</ul>

---

## Contact

Pour toute question ou suggestion, vous pouvez écrire à :  
[contact@moveredocereplacere.fr](mailto:contact@moveredocereplacere.fr)

---

© 2025 Movere Docere Placere — Inspiré par Horace