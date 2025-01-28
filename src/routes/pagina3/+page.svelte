<script>
    import { writable } from 'svelte/store';
  
    // Lista de produtos com nome, preço e imagem
    let products = [
      { id: 1, name: 'Vestido shein', price: 99.99, image: 'vestidoshein.webp' },
      { id: 2, name: 'Blusa shein', price: 59.99, image: 'blusa shein.webp' },
      { id: 3, name: 'Saia shein', price: 89.99, image: 'saia shein.webp' },
      { id: 4, name: 'Calça Jeans shein', price: 120.00, image: 'calçashein.webp' }
    ];
  
    // Estado para o carrinho
    const cart = writable([]);
  
    // Função para adicionar ao carrinho
    function addToCart(product) {
      cart.update((items) => {
        const existingItem = items.find(item => item.id === product.id);
        if (existingItem) {
          return items.map(item => item.id === product.id ? { ...item, quantity: item.quantity + 1 } : item);
        } else {
          return [...items, { ...product, quantity: 1 }];
        }
      });
    }
  
    // Função para limpar o carrinho
    function clearCart() {
      cart.set([]);
    }
  </script>
  
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f8f9fa;
      margin: 0;
      padding: 0;
    }
    .borao{
  position: absolute;
  top:0;
  text-overflow: clip;
      }
    .container {
      padding-top: 30px;
      text-align: center; 
    }
  
    .header {
      text-align: center;
      background-color: #ff66b2;
      color: white;
      padding: 15px;
      font-size: 2rem;
    }
  
    .product-card {
      margin: 20px 0;
      text-align: center;
    }
  
    .product-card img {
      max-width: 100%;
      border-radius: 10px;
    }
  
    .cart-button {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background-color: #ff66b2;
      color: white;
      padding: 15px;
      border: none;
      border-radius: 50%;
      font-size: 20px;
      cursor: pointer;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
    }
  
    .cart-button:hover {
      background-color: #ff3385;
    }
  
    .cart {
      position: fixed;
      bottom: 100px;
      right: 20px;
      background-color: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
      width: 250px;
      text-align: left;
    }
  
    .cart h3 {
      margin-bottom: 10px;
    }
  
    .cart-item {
      margin-bottom: 10px;
    }
  
    .cart-item span {
      display: inline-block;
      margin-right: 10px;
    }
  
    .total {
      font-weight: bold;
      margin-top: 15px;
    }
  
    .clear-button {
      margin-top: 20px;
      background-color: #ff66b2;
      color: white;
      border: none;
      padding: 10px;
      width: 100%;
      cursor: pointer;
      border-radius: 5px;
      transition: background-color 0.3s;
    }
  
    .clear-button:hover {
      background-color: #ff3385;
    }
  </style>
  
  <div class="header">
    <h1>Pink Glam</h1>
    <button class="borao" on:click={() => window.location.href = 'https://mariafumes.github.io/pagina1'}>voltar</button>
  </div>
  
  <div class="container">
    <div class="row">
      {#each products as product}
        <div class="col-md-3 product-card">
          <div class="card" style="width: 18rem;">
            <img src={product.image} class="card-img-top" alt={product.name} />
            <div class="card-body">
              <h5 class="card-title">{product.name}</h5>
              <p class="card-text">R${product.price.toFixed(2)}</p>
              <button class="btn btn-primary" on:click={() => addToCart(product)}>Adicionar ao Carrinho</button>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
  
  <!-- Carrinho de Compras -->
  <div class="cart">
    <h3>Carrinho</h3>
    {#each $cart as item}
      <div class="cart-item">
        <span>{item.name}</span>
        <span>R${item.price.toFixed(2)}</span>
        <span>Quantidade: {item.quantity}</span>
      </div>
    {/each}
  
    {#if $cart.length > 0}
      <div class="total">
        Total: R${$cart.reduce((total, item) => total + item.price * item.quantity, 0).toFixed(2)}
      </div>
      <button class="clear-button" on:click={clearCart}>Limpar Carrinho</button>
    {:else}
      <p>Seu carrinho está vazio.</p>
    {/if}
  </div>
  
  <!-- Botão para visualizar o carrinho -->
  <button class="cart-button" on:click={() => alert('Visualizando Carrinho')}>🛒</button>