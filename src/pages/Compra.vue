<template>
  <section>


    <div class="checkout-container">
      <h2>Finalizar Compra</h2>

      <form @submit.prevent="submitOrder">
        <!-- Informações de Contato -->
        <div class="form-section">
          <h3>Informações de Contato</h3>
          <label for="name">Nome Completo:</label>
          <input type="text" id="name" v-model="contactInfo.name" required />

          <label for="email">Email:</label>
          <input type="email" id="email" v-model="contactInfo.email" required />

          <label for="phone">Telefone:</label>
          <input type="tel" id="phone" v-model="contactInfo.phone" required />
        </div>

        <!-- Endereço de Entrega -->
        <div class="form-section">
          <h3>Endereço de Entrega</h3>
          <label for="address">Endereço:</label>
          <input type="text" id="address" v-model="shippingAddress.address" required />

          <label for="city">Cidade:</label>
          <input type="text" id="city" v-model="shippingAddress.city" required />

          <label for="state">Estado:</label>
          <select id="state" v-model="shippingAddress.state" required>
            <option disabled value="">Selecione um estado</option>
            <option>SP</option>
            <option>RJ</option>
            <option>MG</option>
            <option>RS</option>
            <option>BA</option>
            <!-- Adicione outros estados conforme necessário -->
          </select>

          <label for="zip">CEP:</label>
          <input type="text" id="zip" v-model="shippingAddress.zip" required />
        </div>

        <!-- Método de Pagamento -->
        <div class="form-section">
          <h3>Método de Pagamento</h3>
          <label for="paymentMethod">Escolha um método de pagamento:</label>
          <select id="paymentMethod" v-model="paymentMethod" required>
            <option disabled value="">Selecione um método</option>
            <option>Cartão de Crédito</option>
            <option>Cartão de Débito</option>
            <option>Boleto</option>
            <option>PayPal</option>
            <!-- Adicione outros métodos conforme necessário -->
          </select>

          <div v-if="paymentMethod === 'Cartão de Crédito'">
            <label for="cardNumber">Número do Cartão:</label>
            <input type="text" id="cardNumber" v-model="cardInfo.cardNumber" required />

            <label for="expiryDate">Data de Validade:</label>
            <input type="text" id="expiryDate" v-model="cardInfo.expiryDate" placeholder="MM/AA" required />

            <label for="cvv">CVV:</label>
            <input type="text" id="cvv" v-model="cardInfo.cvv" required />
          </div>
        </div>

        <button type="submit" class="submit-button">Finalizar Compra</button>
      </form>

      <div v-if="errorMessage" class="error-message">{{ errorMessage }}</div>
      <div v-if="successMessage" class="success-message">{{ successMessage }}</div>
    </div>

    <FooterComponent />
  </section>
</template>

<script>
import HeaderComponent from '../components/HeaderComponent.vue';
import FooterComponent from '../components/FooterComponent.vue';

export default {
  name: 'CheckoutPage',
  components: {
    HeaderComponent,
    FooterComponent,
  },
  data() {
    return {
      contactInfo: {
        name: '',
        email: '',
        phone: '',
      },
      shippingAddress: {
        address: '',
        city: '',
        state: '',
        zip: '',
      },
      paymentMethod: '',
      cardInfo: {
        cardNumber: '',
        expiryDate: '',
        cvv: '',
      },
      errorMessage: '',
      successMessage: '',
    };
  },
  methods: {
    submitOrder() {
      // Simulação de envio de pedido
      if (this.validateForm()) {
        this.successMessage = 'Pedido finalizado com sucesso!';
        this.errorMessage = '';
        // Aqui você pode adicionar a lógica para processar o pedido
        console.log('Pedido:', {
          contactInfo: this.contactInfo,
          shippingAddress: this.shippingAddress,
          paymentMethod: this.paymentMethod,
          cardInfo: this.cardInfo,
        });
      } else {
        this.errorMessage = 'Por favor, preencha todos os campos corretamente.';
      }
    },
    validateForm() {
      // Validação básica (ainda pode ser expandida)
      return (
        this.contactInfo.name &&
        this.contactInfo.email &&
        this.contactInfo.phone &&
        this.shippingAddress.address &&
        this.shippingAddress.city &&
        this.shippingAddress.state &&
        this.shippingAddress.zip &&
        this.paymentMethod
      );
    },
  },
};
</script>

<style scoped>
.checkout-container {
  max-width: 600px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #fff;
}

h2 {
  text-align: center;
  margin-bottom: 20px;
  color: #4B0082;
}

.form-section {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}

input,
select {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.submit-button {
  width: 100%;
  padding: 10px;
  background-color: #4B0082;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.submit-button:hover {
  background-color: #720372;
}

.error-message {
  color: red;
  text-align: center;
}

.success-message {
  color: green;
  text-align: center;
}
</style>
