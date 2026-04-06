---
layout: home
title: 🌊 Personalidades da Granja
---

# Bem-vindos ao Arquivo Digital

Aqui celebramos as figuras que marcaram a nossa Praia.

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px;">
{% for pessoa in site.data.conteudo.figuras %}
  <div style="border: 1px solid #ddd; padding: 15px; border-radius: 8px;">
    <img src="{{ pessoa.imagem }}" style="width:100%; border-radius: 5px;">
    <h3>{{ pessoa.nome }}</h3>
    <p>{{ pessoa.bio }}</p>
  </div>
{% endfor %}
</div>

