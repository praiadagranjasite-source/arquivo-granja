---
layout: page
title: Ramalho Ortigão
---

<style>
  /* FORÇAR TAMANHO DA LETRA */
  .post-content, .page-content, #texto-biografia {
    font-size: 1.35rem !important;
    line-height: 1.7 !important;
    color: #1a1a1a !important;
  }
  
  /* POSICIONAR APENAS O ALTIFALANTE À DIREITA */
  .coluna-audio-container {
    display: flex;
    justify-content: flex-end;
    margin-top: -20px; /* Sobe o ícone para ficar alinhado */
    margin-bottom: 20px;
  }

  .btn-coluna {
    font-size: 38px;
    cursor: pointer;
    background: none;
    border: none;
    padding: 0;
  }

  /* ESTILO DAS IMAGENS */
  .img-biografia {
    width: 100%;
    max-width: 500px;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    display: block;
    margin: 25px auto 10px auto;
  }
  .legenda-img {
    text-align: center;
    font-size: 0.95rem;
    color: #666;
    font-style: italic;
    margin-bottom: 25px;
  }
</style>

<div class="coluna-audio-container">
  <button id="btn-coluna" class="btn-coluna">🔊</button>
</div>

<div id="texto-biografia">

Ramalho Ortigão, autor das célebres *"Farpas"*, foi um dos maiores entusiastas da Praia da Granja como local de distinção e saúde.

<img src="https://upload.wikimedia.org/wikipedia/commons/f/f5/Ramalho_Ortigao_01.JPG" class="img-biografia">
<p class="legenda-img">Legenda da primeira foto.</p>

O Estilo de Vida: Ramalho via na Granja o equilíbrio perfeito entre a segurança e a vida social elegante.
 
 Os Banhos de Mar: Como grande defensor do exercício físico e da higiene, Ramalho promoveu os banhos de mar da Granja como terapia para a alma e o corpo.

Ele fazia parte do grupo de intelectuais que transformou esta praia no centro do pensamento português durante os meses de verão.

<img src="https://upload.wikimedia.org/wikipedia/commons/f/f5/Ramalho_Ortigao_01.JPG" class="img-biografia">
<p class="legenda-img">Legenda da segunda foto.</p>

</div>

<script>
  let falando = false;
  document.getElementById('btn-coluna').onclick = function() {
    if (falando) {
      window.speechSynthesis.cancel();
      falando = false;
      this.innerHTML = "🔊";
      return;
    }
    window.speechSynthesis.cancel();
    const texto = document.getElementById('texto-biografia').innerText;
    const msg = new SpeechSynthesisUtterance(texto);
    msg.lang = 'pt-PT';
    window.speechSynthesis.speak(msg);
    falando = true;
    this.innerHTML = "🛑";
    msg.onend = () => { falando = false; this.innerHTML = "🔊"; };
  };
</script>
