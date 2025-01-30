<script>
  let greetingMessage = '';
  let promoMessage = '';
  let showCatalog = false;

  function showGreeting() {
    greetingMessage = 'Obrigado por visitar nossa loja! Estamos ansiosos para ajudá-la a encontrar o look perfeito.';
  }

  function showPromo() {
    promoMessage = 'Aproveite 20% de desconto em todas as peças da coleção de verão! Use o código VERÃO20.';
  }

  function toggleCatalog() {
    showCatalog = !showCatalog;
  }
</script>

<link
  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
  rel="stylesheet"
  integrity="sha384-oTB1D2DRj/qB3UUAsb0x2Djq2v6wtAq3orFl4Bp1DxtDqktwkpPpLLUMflRRXHvH"
  crossorigin="anonymous"
/>
<button class="borao" on:click={() => window.location.href = 'https://mariafumes.github.io/pagina1'}>voltar</button>
<div class="header">
  <h1><b>Pink Glam</b></h1>
  <p>Onde a elegância se encontra com o estilo.</p>
</div>

<div class="container content-section">
  <h2>Sobre a <b>Pink Glam</b></h2>
  <p>Localizada no coração da cidade, a Pink Glam oferece um portfólio incrível de roupas femininas que refletem o estilo, a sofisticação e a ousadia de cada mulher. Desde looks casuais até vestidos de festa, temos a peça perfeita para cada ocasião.</p>
  <p>Com uma equipe especializada e sempre atenta às últimas tendências da moda, garantimos que você saia da nossa loja com uma peça que combine perfeitamente com o seu estilo e personalidade.</p>
</div>

<div class="container content-section">
  <h2>Visite-nos</h2>
  <p>Estamos localizados na Rua das Flores, nº 123, no coração da cidade. Nossa loja é de fácil acesso e está pronta para receber você.</p>
  <p>Se você procura exclusividade, conforto e um atendimento impecável, venha nos visitar e vivencie a experiência de estar em um verdadeiro showroom de roupas.</p>
</div>

<!-- Botões interativos -->
<div class="container text-center">
  <button class="btn btn-primary mt-3" on:click={toggleCatalog}>Ver nosso catálogo</button>
  {#if showCatalog}
    <p class="mt-3">Explore as últimas coleções de roupas da Pink Glam e escolha o seu próximo look favorito!</p>
  {/if}

  <button class="btn btn-success mt-3" on:click={showPromo}>Ver Promoção</button>
  {#if promoMessage}
    <p class="mt-3 text-warning">{promoMessage}</p>
  {/if}
</div>
<div class="footer">
  <p>&copy; 2025 Pink Glam. Todos os direitos reservados.</p>
  <p>Siga-nos no Instagram @pinkglam_oficial</p>
</div>

<style>
  body {
    background-color: #f8f9fa;
    font-family: 'Arial', sans-serif;
  }

  .header {
    background-color: #f8a7cf;
    color: white;
    padding: 40px 0;
    text-align: center;
  }

  .content-section {
    padding: 40px 0;
    text-align: center;
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 30px;
  }

  .content-section h2 {
    color: hsl(330, 86%, 80%);
  }

  .content-section p {
    font-size: 16px;
    color: #555;
    line-height: 1.6;
  }

  .btn-primary {
    background-color: #ffa8d4;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    transition: background-color 0.3s;
  }

  .btn-primary:hover {
    background-color: #fdb5d2;
  }

  .btn-success {
    background-color: #28a745;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    transition: background-color 0.3s;
  }

  .btn-success:hover {
    background-color: #218838;
  }

  .btn-info {
    background-color: #17a2b8;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    transition: background-color 0.3s;
  }

  .btn-info:hover {
    background-color: #138496;
  }

  .footer {
    background-color: #ff66b2;
    color: white;
    text-align: center;
    width: 100%;
    height: 225px;
  }

  .footer p {
    font-size: 14px;
    color: #ccc;
  }
  .borao{
position: absolute;
top:0;
text-overflow: clip;
  }
</style>