<template>
  <section>
    <HeaderComponent/>

    

    <FooterComponent/>
  </section>
</template>

<script>
import axios from 'axios';
import HeaderComponent from '../components/HeaderComponent.vue';
import FooterComponent from '../components/FooterComponent.vue';

export default {
  components: {
    HeaderComponent,
    FooterComponent,
  },
  data() {
    return {
      
    };
  },

  methods: {
  };
</script>

<style scoped>

.meu-fluxo-page { 
  display: flex;
  flex-direction: column;
  flex: 1;
  padding: 50px;
}

.meu-fluxo-infos{
  margin-top: 50px;
  margin-bottom: 100px;
  display: flex;
}

.meu-fluxo-infos-1 {
  display: flex;
  flex-direction: column;
  flex: 1;
  align-items: center;
}

.meu-fluxo-infos-2 {
  display: flex;
  flex-direction: column;
  flex: 1;
  align-items: center;
}

.meu-fluxo-disciplinas-titulo {
  font-size: 20px;
  margin-bottom: 30px;
  font-weight: 600;
}

.progress-container {
  width: 500px; /* Diminuindo a largura da barra de progresso */
  background-color: #e0e0e0;
  border-radius: 25px;
  margin: 20px 0;
}

.progress-bar {
  height: 30px;
  background-color: #4caf50;
  border-radius: 25px;
  text-align: right;
  line-height: 30px;
  color: white;
  position: relative;
}

.progress-text {
  font-size: 24px;
}

.info-header {
  display: flex;
  align-items: center;
  padding: 20px 0;
  border-bottom: 2px solid #e0e0e0;
}

.code {
  font-size: 12px;
  color: #888;
  min-width: 70px;
  margin-right: 10px; /* Espaçamento à direita da checkbox */
}

.discipline-name {
  font-size: 20px;
  color: #333;
  margin-right: 20px;
}

.meu-fluxo-disciplina-lista {
  padding: 20px;
  border-radius: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.progress-span-porc {
  font-weight: 500;
  color: #0b0fdb;
}

.button-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 40px;
  margin-bottom: 20px;
}

.click-button {
  display: flex;
  align-items: center;
  padding: 20px 40px;
  border: none;
  border-radius: 50px;
  background-color: #ffffff;
  box-shadow: 0 0 10px rgba(0, 0, 255, 0.2);
  cursor: pointer;
  transition: box-shadow 0.3s ease;
  position: relative;
}

.click-button span {
  font-size: 18px;
  font-weight: bold;
  color: #091f77;
}

.click-button:hover {
  box-shadow: 0 0 20px rgba(0, 0, 255, 0.4);
}
</style>
