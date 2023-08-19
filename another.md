---
layout: dark
title: About Animals
example: "About animals"
---

This page describes the amazing {{ site.title }} by {{ site.author.name }}. Also showing: {{ site.description }}
{{ page.example }}

## About Animals Pages

{% for animal in site.data.animals %}
- The {{ animal.name }} is a {{ animal.size }} animal.
{% endfor %}

## About **large** animals

{% for animal in site.data.animals %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}- <small>{{ animal.name }}</small>
{% endif %}
{% endfor %}

## List of Small Animals

{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}
