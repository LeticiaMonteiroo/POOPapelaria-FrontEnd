<template>
  <section class="checkout-container">
    <HeaderComponent />
    <div class="produtos-container">
      <div class="form-container">
        <h1>Finalizar Compra</h1>
        <form @submit.prevent="handleSubmit">
          <!-- Formulário de compra -->
          <div class="form-group">
            <label for="nome">Nome Completo:</label>
            <input type="text" id="nome" v-model="formData.nome" required />
          </div>

          <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" v-model="formData.email" required />
          </div>

          <div class="form-group">
            <label for="endereco">Endereço de Entrega:</label>
            <input type="text" id="endereco" v-model="formData.endereco" required />
          </div>

          <div class="form-group">
            <label for="cidade">Cidade:</label>
            <input type="text" id="cidade" v-model="formData.cidade" required />
          </div>

          <div class="form-group">
            <label for="estado">Estado:</label>
            <input type="text" id="estado" v-model="formData.estado" required />
          </div>

          <div class="form-group">
            <label for="cep">CEP:</label>
            <input type="text" id="cep" v-model="formData.cep" required />
          </div>

          <div class="form-group">
            <label>Método de Pagamento:</label>
            <select v-model="formData.metodoPagamento" required>
              <option value="" disabled selected>Selecione...</option>
              <option value="cartao">Cartão de Crédito</option>
              <option value="boleto">Boleto Bancário</option>
              <option value="pix">PIX</option>
            </select>
          </div>

          <button type="submit" class="submit-button">Confirmar Compra</button>
        </form>
      </div>
      <!-- Resumo do Pedido -->
      <div class="resumo-container">
        <h2>Resumo do Pedido</h2>
        <p>Quantidade de Itens: {{ quantidadeItens }}</p>
        <p>Valor Total: R$ {{ valorTotal.toFixed(2) }}</p>
      </div>
    </div>
    <FooterComponent />
  </section>
</template>

<script>
import HeaderComponent from '../components/HeaderComponent.vue';
import FooterComponent from '../components/FooterComponent.vue';

export default {
  name: 'Compra',
  components: {
    HeaderComponent,
    FooterComponent,
  },
  data() {
    return {
      formData: {
        nome: '',
        email: '',
        endereco: '',
        cidade: '',
        estado: '',
        cep: '',
        metodoPagamento: '',
      },
      quantidadeItens: 0,
      valorTotal: 0.00,
    };
  },
  created() {
    this.calcularResumoCarrinho();
  },
  methods: {
    // Função para calcular a quantidade de itens e o valor total diretamente do localStorage
    calcularResumoCarrinho() {
      const carrinho = JSON.parse(localStorage.getItem('carrinho') || '[]');
      let quantidade = 0;
      let valor = 0.00;

      carrinho.forEach(item => {
        quantidade += item.quantidade;
        valor += item.quantidade * item.preco;
      });

      this.quantidadeItens = quantidade;
      this.valorTotal = valor;

      console.log("Quantidade de itens:", quantidade);
      console.log("Valor total:", valor.toFixed(2));
    },
    handleSubmit() {
      console.log('Dados do formulário:', this.formData);
      alert('Compra confirmada!');
      this.resetForm();
    },
    resetForm() {
      this.formData = {
        nome: '',
        email: '',
        endereco: '',
        cidade: '',
        estado: '',
        cep: '',
        metodoPagamento: '',
      };
    },
  },
};
</script>

<style scoped>
.checkout-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.produtos-container {
  display: flex;
  justify-content: space-between;
  padding: 20px;
}

.form-container {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 30px;
  max-width: 600px;
  width: 100%;
}

.resumo-container {
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 20px;
  max-width: 300px;
  width: 100%;
}

h1, h2 {
  text-align: center;
  margin-bottom: 20px;
}

p {
  font-size: 18px;
  margin-bottom: 10px;
}

.submit-button {
  background-color: #4B0082;
  color: white;
  padding: 15px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  width: 100%;
}

.submit-button:hover {
  background-color: #3c0071;
}
</style>
