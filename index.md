---
layout: home
title: 🌊 Arquivo Praia da Granja
---

# Personalidades Históricas da Granja

Aqui celebramos as figuras que marcaram a nossa Praia.

<div style="display: grid; grid-template-columns: 1fr; gap: 20px;">
{% for pessoa in site.data.conteudo.figuras %}
  <div style="border: 1px solid #ddd; padding: 20px; border-radius: 10px; background: #fafafa; box-shadow: 2px 2px 5px rgba(0,0,0,0.05);">
    <h2 style="margin-top: 0; color: #2c3e50;">{{ pessoa.nome }}</h2>
    <p style="font-style: italic; color: #555;">{{ pessoa.bio }}</p>
    <a href="{{ site.baseurl }}{{ pessoa.link }}" style="display: inline-block; padding: 10px 20px; background: #007bff; color: white; text-decoration: none; border-radius: 5px; font-weight: bold; font-size: 0.9em;">Ler biografia completa →</a>
  </div>
{% endfor %}
</div>
