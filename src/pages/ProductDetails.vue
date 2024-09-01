<template>
    <div>
      <HeaderComponent />
      <div class="product-details">
        <img :src="produto.imagem" alt="Imagem do produto" class="product-image" />
        <h1>{{ produto.nome }}</h1>
        <p>{{ produto.descricao }}</p>
        <p>Preço: {{ produto.preco }}</p>
        <p>Categoria: {{ produto.categoria }}</p>
        <p>Estoque: {{ produto.estoque }}</p>
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
  /* Adicione estilos para a página de detalhes */
  </style>
  