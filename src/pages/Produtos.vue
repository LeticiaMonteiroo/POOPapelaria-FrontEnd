<template>
  <div>
    <HeaderComponent />
    <div class="containerSelecao">
      <div class="container-selecao-title">Qualidade Garantida & Satisfação Completa!</div>

      <div class="contentSelecao">
        <router-link
          v-for="(produto, index) in produtos"
          :key="index"
          :to="{ name: 'ProdutoDetalhes', params: { id: produto.codigo } }"
          class="produto-card"
        >
          <img :src="produto.imagem" alt="Imagem do produto" class="produto-imagem" />
          <div class="produto-nome">{{ produto.nome }}</div>
        </router-link>
      </div>
    </div>

    <FooterComponent />
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import HeaderComponent from '../components/HeaderComponent.vue';
import FooterComponent from '../components/FooterComponent.vue';

export default defineComponent({
  components: {
    HeaderComponent,
    FooterComponent
  },
  name: 'Loja',
  data() {
    return {
      produtos: [
        {
          nome: 'Caderno Espiral',
          codigo: '001',
          preco: 'R$ 19,90',
          descricao: 'Caderno espiral 200 folhas, capa dura com design moderno.',
          categoria: 'Papelaria',
          estoque: 50,
          imagem: 'https://cdnv2.moovin.com.br/marbig/imagens/produtos/original/caderno-espiral-capa-dura-universitario-1-materia-zip-preto-80-folhas-img-199485_3008240519028644.jpg'
        },
        {
          nome: 'Caneta Esferográfica',
          codigo: '002',
          preco: 'R$ 2,50',
          descricao: 'Caneta esferográfica azul de ponta fina, ideal para escrita suave.',
          categoria: 'Papelaria',
          estoque: 200,
          imagem: 'https://via.placeholder.com/260'
        },
        {
          nome: 'Mochila Escolar',
          codigo: '003',
          preco: 'R$ 120,00',
          descricao: 'Mochila escolar resistente, com vários compartimentos.',
          categoria: 'Acessórios',
          estoque: 30,
          imagem: 'https://via.placeholder.com/260'
        }
      ]
    };
  }
});
</script>

<style scoped>
.containerSelecao {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 20px;
  max-width: 1140px;
  margin: 20px auto;
}

.container-selecao-title {
  font-size: 24px;
  margin-bottom: 20px;
  color: #720372;
  text-align: center;
  font-weight: 600;
  justify-content: center;
}

.contentSelecao {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: space-between;
}

.produto-card {
  background-color: #f9f9f9;
  border-radius: 8px;
  padding: 10px;
  width: calc(30.333% - 20px);
  text-align: center;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
  height: 300px; /* Aumentei a altura para 300px */
  text-decoration: none; /* Remove o sublinhado dos links */
  color: inherit; /* Herda a cor do texto do pai */
}

.produto-card:hover {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Adiciona um efeito de hover */
}

.produto-imagem {
  max-width: 100%;
  border-radius: 4px;
}

.produto-nome {
  font-size: 16px;
  margin-top: 10px;
  font-weight: 500;
  color: rgb(4, 4, 53);
}
</style>
