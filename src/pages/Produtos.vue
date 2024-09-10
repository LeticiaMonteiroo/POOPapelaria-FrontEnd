<template>
  <section>
    <HeaderComponent/>

    <!-- Conteúdo principal -->
    <div class="produtos-container">
      <div class="container-selecao-title">Sua criatividade começa aqui!</div>

      <!-- Container de produtos -->
      <div class="produtos-grid">
        <div 
          class="produto-item" 
          v-for="produto in produtos" 
          :key="produto.id"
          @click="goToDetalhes(produto.id)"
        >
          <div class="produto-info">
            <h3>{{ produto.nome }}</h3>
            <div class="foto-container">
              <img :src="`/assets/${produto.imagem}`" :alt="produto.nome" />
            </div>
            <p class="avaliacoes">{{ produto.avaliacoes }} Avaliações</p>
            <p class="preco">{{ produto.preco }}</p>
          </div>
        </div>
      </div>
    </div>

    <FooterComponent/>
  </section>
</template>

<script>
import HeaderComponent from '../components/HeaderComponent.vue';
import FooterComponent from '../components/FooterComponent.vue';

export default {
  name: 'ProdutosPage',
  components: {
    HeaderComponent,
    FooterComponent
  },
  data() {
    return {
      produtos: [
        {
          id: 1,
          nome: 'Caneta Esferográfica Compactor -JET LUX- Mentos c/4 cores',
          preco: 'R$ 11,99',
          avaliacoes: '45',
          imagem: 'https://m.media-amazon.com/images/G/32/apparel/rcxgs/tile._CB483369971_.gif' // Nome do arquivo na pasta public/assets
        },
        {
          id: 2,
          nome: 'Caderno Universitário - 10 Matérias',
          preco: 'R$ 29,99',
          avaliacoes: '30',
          imagem: 'caderno-universitario.png' // Nome do arquivo na pasta public/assets
        },
        {
          id: 3,
          nome: 'Mochila Escolar - Preto',
          preco: 'R$ 89,99',
          avaliacoes: '20',
          imagem: 'mochila-escolar.png' // Nome do arquivo na pasta public/assets
        },
        {
          id: 4,
          nome: 'Caneta Esferográfica Compactor -JET LUX- Mentos c/4 cores',
          preco: 'R$ 11,99',
          avaliacoes: '45',
          imagem: 'mais-vendido-caneta-mentos.png' // Nome do arquivo na pasta public/assets
        },
        {
          id: 5,
          nome: 'Caderno Universitário - 10 Matérias',
          preco: 'R$ 29,99',
          avaliacoes: '30',
          imagem: 'caderno-universitario.png' // Nome do arquivo na pasta public/assets
        },
        {
          id: 6,
          nome: 'Mochila Escolar - Preto',
          preco: 'R$ 89,99',
          avaliacoes: '20',
          imagem: 'mochila-escolar.png' // Nome do arquivo na pasta public/assets
        },
        // Adicione mais produtos aqui
      ]
    };
  },
  methods: {
    goToDetalhes(id) {
      this.$router.push({ name: 'DetalhesProduto', params: { produtoId: id } });
    }
  }
};
</script>

<style scoped>
.container-selecao-title {
  font-size: 24px;
  margin-bottom: 20px;
  color: #720372;
  text-align: center;
  font-weight: 600;
}

.produtos-container {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 30px;
  max-width: 1100px;
  margin: 20px auto;
}

.produtos-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 produtos por linha */
  gap: 20px;
}

.produto-item {
  background-color: #fff;
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  cursor: pointer; /* Indicando que é clicável */
  transition: transform 0.3s ease;
}

.produto-item:hover {
  transform: scale(1.05); /* Efeito de zoom ao passar o mouse */
}

.foto-container {
  margin: 20px 0; /* Espaçamento acima e abaixo da imagem */
}

.foto-container img {
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.texto-produto h3 {
  font-size: 18px;
  margin-bottom: 10px;
  color: #333;
}

.texto-produto .avaliacoes {
  font-size: 14px;
  color: #5a849f;
  margin-bottom: 5px;
}

.texto-produto .preco {
  font-size: 16px;
  font-weight: bold;
  color: #4B0082;
}
</style>
