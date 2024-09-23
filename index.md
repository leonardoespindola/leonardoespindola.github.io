---
title: Leonardo Espindola
layout: splash
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/splash4.webp
  actions:
    - label: "Youtube"
      icon: "fab fa-fw fa-youtube"
      url: "https://www.youtube.com/@leonardo-espindola"
    - label: "Linkedin"
      icon: "fab fa-fw fa-youtube"
      url: "https://www.linkedin.com/in/leonardoespindola"
excerpt: "Soy ingeniero e investigador de la calidad y testing"
---

Aquí encontrarás contenido dedicado a la calidad de software, con un enfoque en la mejora continua, automatización de procesos y estrategias innovadoras para la optimización del rendimiento en entornos tecnológicos complejos. Comparto conocimientos y experiencias para ayudar a mejorar la eficiencia y asegurar la calidad en cada fase del ciclo de desarrollo.

# Que otras cosas vas a encontrar

  - Conferencias relacionadas a la calidad.
  - Videos de testing y herramientas afines.
  - IA aplicado al Testing.
  - Acceso a scripts de automatizacion en mi repositorio github (proximamente).

# Lo ultimo del Blog

<ul style="list-style-type: none; padding: 0;">
  {% assign workaround = "" %}
  {% for post in site.posts reversed limit:2 %}
    {% capture onePost %}
    <li style="margin-bottom: 20px; display: flex; align-items: center;">
      <!-- Mostrar la imagen teaser si está definida en el front matter -->
      {% if post.header.teaser %}
        <img src="{{ post.header.teaser }}" alt="{{ post.title }}" style="width:150px;height:auto; margin-right: 15px; border-radius: 8px;">
      {% endif %}
      <div>
        <div style="font-size: 0.8em; color: #666;">{{ post.date | date: "%e. %B %Y" }}</div>
        <h3 style="margin-top: 0;"><a href="{{ post.url }}" style="text-decoration: none; color: #333;">{{ post.title }}</a></h3>
        <div>
          {{ post.excerpt }}
        </div>
      </div>
    </li>
    {% endcapture %}
    {% assign workaround = workaround | prepend: onePost %}
  {% endfor %}
  {{ workaround }}
</ul>