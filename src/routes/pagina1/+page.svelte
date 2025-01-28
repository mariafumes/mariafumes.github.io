<script>
    let menuOpen = false;
  
    function toggleMenu() {
      menuOpen = !menuOpen;
    }
  </script>
  
  <style>
    body {
      margin: 0;
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to bottom right, #ff7eb3, #ff758c);
      color: white;
    }
  
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      background-color: rgba(255, 140, 226, 0.5);
      box-shadow: 0 4px 6px rgba(248, 0, 215, 0.2);
    }
  
    header h1 {
      text-align: center;
      margin: 0;
      font-size: 1.8rem;
    }
  
    nav {
      display: flex;
      gap: 1.5rem;
    }
  
    nav a {
      text-decoration: none;
      color: white;
      font-size: 1.2rem;
      transition: color 0.3s;
    }
  
    nav a:hover {
      color: #ffb3c7;
    }
  
    .menu-button {
      background: none;
      border: 2px solid white;
      border-radius: 0.5rem;
      color: white;
      padding: 0.5rem 1rem;
      font-size: 1rem;
      cursor: pointer;
      transition: background 0.3s, transform 0.2s;
    }
  
    .menu-button:hover {
      background: white;
      color: #ff7eb3;
    }
  
    .menu-button:active {
      transform: scale(0.95);
    }
  
    .hero {
      text-align: center;
      padding: 4rem 2rem;
      margin: 0 auto;
    }
  
    .hero h2 {
      font-size: 2.5rem;
      margin-bottom: 1rem;
    }
  
    .hero p {
      font-size: 1.2rem;
      max-width: 600px;
      margin: 0 auto;
    }
  
    .button-group {
      margin-top: 2rem;
    }
  
    .button-group a {
      text-decoration: none;
      display: inline-block;
      background-color: #ffb3c7;
      color: white;
      padding: 0.75rem 1.5rem;
      border-radius: 1rem;
      font-size: 1.1rem;
      margin: 0 0.5rem;
      transition: background 0.3s;
    }
  
    .button-group a:hover {
      background-color: #ff758c;
    }
  
    .info-section {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
      padding: 2rem;
    }
  
    .info-card {
      background: rgba(255, 255, 255, 0.1);
      border-radius: 1rem; 
      padding: 1.5rem;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
      text-align: center;
    }
  
    .info-card h3 {
      font-size: 1.5rem;
      margin-bottom: 0.5rem;
    }
  
    .info-card p {
      font-size: 1rem;
      color: #fd81f3;
    }
  </style>
  
  <main>
    <header>
      <h1>Pink glam</h1>
      <nav>
        <a href="/maria2">Sobre</a>
        <a href="">19-99991122</a>
        <button class="menu-button" on:click={toggleMenu}>
          {menuOpen ? 'Fechar' : 'Menu'}
        </button>
      </nav>
    </header>
  
    <section class="hero">
      <h2>Bem-vinda à sua nova loja favorita!</h2>
      <p>Descubra roupas incríveis para todas as ocasiões. Compre com estilo, confiança e conforto!</p>
      <div class="button-group">
        <a href="/maria3">Ver Produtos</a>
      </div>
    </section>
  
    <section class="info-section">
      <div class="info-card">
        <h3>Moda Exclusiva</h3>
        <p><b>Peças únicas e exclusivas que refletem sua personalidade.</b></p>
      </div>
      <div class="info-card">
        <h3>Conforto Garantido</h3>
        <p><b>Roupas feitas com materiais de alta qualidade para o seu conforto.</b></p>
      </div>
      <div class="info-card">
        <h3>Atendimento Premium</h3>
        <p><b>Uma experiência de compra personalizada e inesquecível.</b></p>
      </div>
    </section>
  </main>
  