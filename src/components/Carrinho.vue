<template>
    <section class="main-container">
      <HeaderComponent />
      <div>
        <h1>Seu Carrinho de Compras</h1>
        <div v-if="cart.length > 0">
          <ul>
            <li v-for="(produto, index) in cart" :key="index" class="produto-item">
              <img :src="produto.imagem" :alt="produto.nome" class="produto-imagem" />
              <div class="produto-info">
                <h2>{{ produto.nome }}</h2>
                <p>{{ produto.preco }}</p>
                <button @click="removeFromCart(index)">Remover</button>
              </div>
            </li>
          </ul>
          <p><strong>Total: {{ totalCartPrice }}</strong></p>
        </div>
        <div v-else>
          <p>Seu carrinho está vazio.</p>
        </div>
      </div>
      <FooterComponent />
    </section>
  </template>
  
  <script>
  import HeaderComponent from '../components/HeaderComponent.vue';
  import FooterComponent from '../components/FooterComponent.vue';
  
  export default {
    name: 'Carrinho',
    components: {
      HeaderComponent,
      FooterComponent,
    },
    data() {
      return {
        cart: [],
      };
    },
    computed: {
      totalCartPrice() {
        return this.cart.reduce((total, produto) => {
          const preco = parseFloat(produto.preco.replace('R$', '').replace(',', '.'));
          return total + preco;
        }, 0).toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
      },
    },
    mounted() {
      // Carrega o carrinho do localStorage quando o componente é montado
      const storedCart = JSON.parse(localStorage.getItem('cart'));
      if (storedCart) {
        this.cart = storedCart;
      }
    },
    methods: {
      removeFromCart(index) {
        // Remove o produto do carrinho pelo índice
        this.cart.splice(index, 1);
        // Atualiza o localStorage
        localStorage.setItem('cart', JSON.stringify(this.cart));
      },
    },
  };
  </script>
  
  <style scoped>
  /* Estilização do carrinho */
  .produto-item {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }
  .produto-imagem {
    width: 100px;
    height: 100px;
    margin-right: 20px;
  }
  .produto-info {
    display: flex;
    flex-direction: column;
  }
  </style>
  