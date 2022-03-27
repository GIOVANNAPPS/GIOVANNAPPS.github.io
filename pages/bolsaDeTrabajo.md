---
layout              : page
title               : "Bolsa De Trabajo"
meta_title          : 
subheadline         : 
teaser              : 
permalink           : "/bolsadetrabajo/"
---

{% assign busco = site.trabajo | where:"type", "busco" %}
{% assign ofrezco = site.trabajo | where:"type", "ofrezco" %}
{% assign todaySeconds = 'now' | date: '%s' %}

### Ofertas de Servicios

{% for t in ofrezco %}
  {% assign venceSeconds = t.vence | date: '%s' %}
  {% if venceSeconds > todaySeconds %}
* [{{ t.title }} ({{t.contacto}})]({{ t.url }})
  {% endif %}
{% endfor %}

### Ofertas de Empleo

{% for t in busco %}
  {% assign venceSeconds = t.vence | date: '%s' %}
  {% if venceSeconds > todaySeconds %}
* [{{ t.title }} ({{t.contacto}})]({{ t.url }})
  {% endif %}
{% endfor %}