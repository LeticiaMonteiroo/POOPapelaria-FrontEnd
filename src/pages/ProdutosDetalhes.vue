<template>
  <section class="main-container">
    <HeaderComponent />
    <div class="produtos-container">
      <div v-if="produto" class="detalhes-container">
        <div class="foto-container">
          <img :src="produto.imagem" :alt="produto.nome" class="produto-imagem" />
        </div>
        <div class="info-container">
          <h1 class="produto-nome">{{ produto.nome }}</h1>
          <p class="produto-preco">{{ produto.preco }}</p>
          <p class="produto-avaliacoes">{{ produto.avaliacoes }} Avaliações</p>
          <p class="produto-descricao">{{ produto.descricao }}</p>
        </div>
      </div>
    </div>
    <FooterComponent />
  </section>
</template>

<script>
import HeaderComponent from '../components/HeaderComponent.vue';
import FooterComponent from '../components/FooterComponent.vue';

export default {
  name: 'DetalhesProduto',
  components: {
    HeaderComponent,
    FooterComponent,
  },
  data() {
    return {
      produto: null,
      produtos: [
        // Lista de produtos
        {
      
          id: 1,
          nome: 'Caderno Universitário - 10 Matérias',
          preco: 'R$ 29,99',
          avaliacoes: '30',
          imagem: 'https://m.media-amazon.com/images/I/51qt5Zw+CUL._AC_SY300_SX300_.jpg',
        },
        {
          id: 2,
          nome: 'Mochila Feminina Escolar Bolsa Faculdade Viagem Anti Furto para Notebook',
          preco: 'R$ 89,99',
          avaliacoes: '20',
          imagem: 'https://m.media-amazon.com/images/I/61SSmqSt+OL._AC_SX679_.jpg',
        },
        {
          id: 3,
          nome: 'Estojo Escolar Feminino Masculino Grande Box Ziper',
          preco: 'R$ 33,60',
          avaliacoes: '15',
          imagem: 'https://m.media-amazon.com/images/I/71Bh-44GxtL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 4,
          nome: 'Caderno Executivo Costurado Capa Dura Fitto G Cambridge Rosa 90 Gramas 80 Folhas',
          preco: 'R$ 35,90',
          avaliacoes: '53',
          imagem: 'https://m.media-amazon.com/images/I/51A54xjw-dL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 5,
          nome: 'STABILO point 88 – Caneta Ponta Fina – Estojo com 15 unidades – Em 15 cores',
          preco: 'R$ 120,90',
          avaliacoes: '20',
          imagem: 'https://m.media-amazon.com/images/I/81zKoOj50SL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 6,
          nome: 'Agenda Planner 2024 - Capa Floral, 160 Páginas',
          preco: 'R$ 45,90',
          avaliacoes: '35',
          imagem: 'https://m.media-amazon.com/images/I/6141U732frL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 7,
          nome: 'Lápis de Cor Aquarelável 12 Cores',
          preco: 'R$ 29,90',
          avaliacoes: '40',
          imagem: 'https://m.media-amazon.com/images/I/51Qo-e1jLBL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 8,
          nome: 'Kit de Canetas Gel Neon c/ 12 Unidades',
          preco: 'R$ 25,99',
          avaliacoes: '60',
          imagem: 'https://m.media-amazon.com/images/I/61RSaboiFDL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 9,
          nome: 'Caderno Inteligente – Tamanho Grande, Folhas Pautadas',
          preco: 'R$ 135,90',
          avaliacoes: '45',
          imagem: 'https://m.media-amazon.com/images/I/51pNysYjzFL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 10,
          nome: 'Pasta de Documentos ACP 1134',
          preco: 'R$ 85,00',
          avaliacoes: '25',
          imagem: 'https://m.media-amazon.com/images/I/61qqk93VvNL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 11,
          nome: 'Caneca Térmica Inox com Tampa - 500ml',
          preco: 'R$ 49,99',
          avaliacoes: '32',
          imagem: 'https://encrypted-tbn3.gstatic.com/shopping?q=tbn:ANd9GcRQvXoneq5g24BPFNdaWrS3M62yMNUP5pm3Uyiowx8HWf-aWt7M5im2GA2MpkYl2nW8Wtvd7wwcOGkICYbfDbriTyZPdrSzGEeSCYtTAW0pv9Nq6ho0x-3f0A&usqp=CAE',
        },
        {
          id: 12,
          nome: 'Organizador de Mesa com Portas-canetas',
          preco: 'R$ 55,00',
          avaliacoes: '15',
          imagem: 'https://encrypted-tbn3.gstatic.com/shopping?q=tbn:ANd9GcS-MQHQkPpAuuI4oGCyKrYphpyXuXrN4Czi1u109OPIuQCpaVmgWi5CV9jmdCyoVnKGO_-O0lL-ncuKnSmS1RqFkJgyR19iKTomOwA43bzl&usqp=CAE',
        },
        {
          id: 13,
          nome: 'Caneta Esferográfica Premium - Estojo com 4 Unidades',
          preco: 'R$ 39,90',
          avaliacoes: '22',
          imagem: 'https://encrypted-tbn2.gstatic.com/shopping?q=tbn:ANd9GcRWaCrDv8Ajjks5-9TnyCr7zUZ644zqYsuuZr3USV92qoSl11SLU7D6LdJD7E_vckEzos-RRuSa_yOIz6SKP6EK95RPmU0Q1E-0rdX1iKY&usqp=CAE',
        },
        {
          id: 14,
          nome: 'Bloco de Notas Adesivas Coloridas - 400 Folhas',
          preco: 'R$ 21,50',
          avaliacoes: '28',
          imagem: 'https://m.media-amazon.com/images/I/61sg2Z+W6NL._AC_SX300_SY300_.jpg',
        },
        {
          id: 15,
          nome: 'Marcador de Texto Fluorescente Stabilo Boss Pastel c/ 6 Unidades',
          preco: 'R$ 36,90',
          avaliacoes: '50',
          imagem: 'https://achalajournal.com.br/wp-content/uploads/2024/01/achala-journal-stabilo-boss-shine-kit-6.png',
        },
        {
          id: 16,
          nome: 'Marcador Artístico Permanente Evoke Ponta Fina, Blister com 12 Unidades',
          preco: 'R$ 55,90',
          avaliacoes: '24',
          imagem: 'https://m.media-amazon.com/images/I/81TcWQ6d9lL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        {
          id: 17,
          nome: 'Lapiseira 0.5mm com Grip Ergonômico',
          preco: 'R$ 19,80',
          avaliacoes: '37',
          imagem: 'https://m.media-amazon.com/images/I/51wSjSZScEL.__AC_SX300_SY300_QL70_ML2_.jpg',
        },
        ],
    };
  },
  mounted() {
    // Obtém o ID do produto da URL
    const produtoId = parseInt(this.$route.params.produtoId);
    // Encontra o produto correspondente
    this.produto = this.produtos.find(p => p.id === produtoId);
  },
};
</script>

<style scoped>
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
}

body {
  display: flex;
  flex-direction: column;
  min-height: 100vh; /* Garante que o corpo ocupe pelo menos a altura da tela */
}

.main-container {
  flex: 1; /* Faz com que o main-container ocupe o espaço restante */
  display: flex;
  flex-direction: column;
}

header {
  flex-shrink: 0; /* Não permite que o cabeçalho encolha */
}

footer {
  flex-shrink: 0; /* Não permite que o rodapé encolha */
}

.produtos-container {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 30px;
  margin: 20px auto;
  max-width: 1100px; /* Largura fixa para o container principal */
  width: 100%; /* Garante que o container use 100% da largura disponível, até o máximo definido */
  overflow: hidden; /* Esconde qualquer conteúdo que ultrapasse a largura do container */
}

.detalhes-container {
  display: flex;
  gap: 20px;
  align-items: flex-start; /* Garante que os itens dentro do container estejam alinhados no início */
}

.foto-container {
  flex: 0 0 400px; /* Tamanho fixo para a foto */
}

.produto-imagem {
  width: 100%;
  height: 400px; /* Altura fixa para a imagem */
  object-fit: cover;
  border-radius: 8px;
  margin-left: 60px;
}

.info-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.produto-nome {
  font-size: 2em; /* Ajuste conforme necessário */
  font-weight: bold;
  color: #6a1b9a; /* Roxo escuro */
  margin-bottom: 10px;
  overflow-wrap: break-word; /* Quebra a palavra se necessário */
  margin-left: 56px;
}

.produto-preco {
  font-size: 1.6em; /* Ajuste conforme necessário */
  color: #333;
  margin-bottom: 10px;
  margin-left: 56px;
}

.produto-avaliacoes {
  font-size: 1.4em; /* Ajuste conforme necessário */
  color: #555;
  margin-bottom: 20px;
  margin-left: 56px;
}

.produto-descricao {
  font-size: 1.2em; /* Ajuste conforme necessário */
  color: #666;
}
</style>