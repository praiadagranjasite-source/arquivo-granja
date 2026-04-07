---
layout: page
title: Ramalho Ortigão
---

<style>
  /* FORÇAR TAMANHO DA LETRA E LEGIBILIDADE */
  .post-content, .page-content, #texto-biografia {
    font-size: 1.35rem !important;
    line-height: 1.7 !important;
    color: #1a1a1a !important;
    font-family: 'Georgia', serif; /* Fonte mais clássica para biografias */
  }
  
  /* ESTILO DO TÍTULO E BOTÃO */
  .header-biografia {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
    border-bottom: 2px solid #eee;
    padding-bottom: 15px;
  }
  .titulo-principal {
    font-size: 2.6rem !important;
    margin: 0 !important;
    font-family: sans-serif;
  }
  
  /* ESTILO DAS IMAGENS NA BIOGRAFIA */
  .img-biografia {
    width: 100%;
    max-width: 500px;
    height: auto;
    border-radius: 12px; /* Cantos arredondados */
    box-shadow: 0 4px 10px rgba(0,0,0,0.15); /* Sombra suave */
    display: block;
    margin: 25px auto 10px auto; /* Centrada com espaço */
  }
  .legenda-img {
    text-align: center;
    font-size: 0.95rem;
    color: #666;
    font-style: italic;
    margin-bottom: 25px;
  }
</style>

<div class="header-biografia">
  <h1 class="titulo-principal">{{ page.title }}</h1>
  <button id="btn-coluna" style="font-size: 38px; cursor: pointer; background: none; border: none; padding: 0;">🔊</button>
</div>

<div id="texto-biografia">

  Ramalho Ortigão e o Veraneio na Granja

Ramalho Ortigão, 
Autor das célebres "Farpas", 
Foi um dos maiores entusiastas da Praia da Granja como local de distinção e saúde.

<img src="https://upload.wikimedia.org/wikipedia/commons/e/ed/Retrato_de_Ramalho_Ortig%C3%A3o_-_Columbano_Bordalo_Pinheiro.jpg" class="img-biografia" alt="Retrato de Ramalho Ortigão por Columbano Bordalo Pinheiro">
<p class="legenda-img">Retrato de Ramalho Ortigão por Columbano Bordalo Pinheiro, c. 1888-1890.</p>

 O Estilo de Vida: 
Ramalho via na Granja o equilíbrio perfeito entre o repouso e a vida social elegante.
Os Banhos de Mar:
Como grande defensor do exercício físico e da higiene, Ramalho promoveu os banhos de mar da Granja como terapia para a alma e o corpo.

Ele fazia parte do grupo de intelectuais que transformou esta praia no centro do pensamento português durante os meses de verão.

<img src="https://static.wixstatic.com/media/745c34_e36f82ed6b9482dab5fc525990a856e7.jpeg/v1/fill/w_428,h_580,al_c,lg_1,q_80,enc_auto/745c34_e36f82ed6b9482dab5fc525990a856e7.jpeg" class="img-biografia" alt="Vista antiga da Praia da Granja">
<p class="legenda-img">A Praia da Granja no século XIX, frequentada pela elite intelectual. (Imagem provisória)</p>

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
    // Captura apenas o texto da div biografia
    const texto = document.getElementById('texto-biografia').innerText;
    const msg = new SpeechSynthesisUtterance(texto);
    msg.lang = 'pt-PT'; // Voz de Portugal
    msg.rate = 1.0;

    window.speechSynthesis.speak(msg);
    falando = true;
    this.innerHTML = "🛑"; // Muda para parar enquanto fala

    msg.onend = () => {
      falando = false;
      this.innerHTML = "🔊";
    };
  };
</script>

