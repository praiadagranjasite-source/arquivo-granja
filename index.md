---
layout: home
title: 🌊 Arquivo Praia da Granja
---

# Personalidades Históricas da Granja

Aqui celebramos as figuras que marcaram a nossa Praia.

<div style="display: grid; grid-template-columns: 1fr; gap: 30px;">
{% for pessoa in site.data.conteudo.figuras %}
  <div style="border: 1px solid #ddd; padding: 20px; border-radius: 10px; background: #fafafa; box-shadow: 2px 2px 8px rgba(0,0,0,0.1); text-align: center;">
    
    {% if pessoa.imagem %}
      <img src="{{ pessoa.imagem }}" style="width: 100%; max-width: 450px; height: auto; border-radius: 8px; margin-bottom: 15px; display: block; margin-left: auto; margin-right: auto;">
    {% endif %}

    <h2 style="margin-top: 0; color: #2c3e50; font-size: 1.8em;">{{ pessoa.nome }}</h2>
    
    <p style="font-style: italic; color: #555; margin-bottom: 15px; font-size: 1.1em;">{{ pessoa.bio }}</p>
    
    {% if pessoa.link %}
      <a href="{{ site.baseurl }}{{ pessoa.link }}" style="display: inline-block; padding: 12px 25px; background: #007bff; color: white; text-decoration: none; border-radius: 30px; font-weight: bold; font-size: 1em; transition: background 0.3s ease;">Ler biografia completa →</a>
    {% endif %}
    
  </div>
{% endfor %}
</div>
