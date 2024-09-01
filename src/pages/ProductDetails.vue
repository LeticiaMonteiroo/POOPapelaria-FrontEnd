<template>
    <div>
      <HeaderComponent />
      <div class="product-details">
        <div class="product-image-container">
          <img :src="produto.imagem" alt="Imagem do produto" class="product-image" />
        </div>
        <div class="product-info">
          <h1 class="product-name">{{ produto.nome }}</h1>
          <p>{{ produto.descricao }}</p>
          <p>Preço: {{ produto.preco }}</p>
          <p>Categoria: {{ produto.categoria }}</p>
          <p>Estoque: {{ produto.estoque }}</p>
        </div>
      </div>
      <FooterComponent />
    </div>
  </template>
  
  <script>
  import { defineComponent } from 'vue';
  import HeaderComponent from '../components/HeaderComponent.vue';
  import FooterComponent from '../components/FooterComponent.vue';
  import axios from 'axios';
  
  export default defineComponent({
    components: {
      HeaderComponent,
      FooterComponent
    },
    data() {
      return {
        produto: {}
      };
    },
    async created() {
      const id = this.$route.params.id;
      await this.getProductDetails(id);
    },
    methods: {
      async getProductDetails(id) {
        try {
          const response = await axios.get(`http://localhost:8000/api/produtos/${id}`);
          this.produto = response.data;
        } catch (err) {
          console.error('Erro ao buscar os detalhes do produto:', err);
        }
      }
    }
  });
  </script>
  
  <style scoped>
  .product-details {
    display: flex;
    flex-direction: row;
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto;
    gap: 20px;
  }
  
  .product-image-container {
    flex: 1;
    max-width: 500px;
  }
  
  .product-image {
    width: 100%;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  .product-info {
    flex: 2;
    padding: 20px;
  }
  
  .product-name {
    font-size: 36px; /* Tamanho grande para o nome do produto */
    font-weight: bold;
    margin-bottom: 15px;
  }
  
  .product-info p {
    font-size: 18px;
    margin-bottom: 10px;
  }
  
  .product-info p:last-of-type {
    margin-bottom: 0;
  }
  </style>
