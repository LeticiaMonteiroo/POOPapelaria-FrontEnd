<template>
  <section>
    <HeaderComponent/>

    <!-- Conteúdo principal -->
    <div class="containerDisciplina">
      <div class="container-selecao-title">Qualidade Garantida & Satisfação Completa!</div>
      
      <!-- Container de serviços -->
      <div class="services-container">
        <div 
          v-for="item in services" 
          :key="item.code" 
          class="service-container"
        >
          <div class="service-left">
            <div class="service-square">
              <!-- Adicionando a imagem do serviço -->
              <img :src="item.image" :alt="item.title" class="service-image" />
            </div>
          </div>
          <div class="service-right">
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
            <p><strong>Materiais:</strong> {{ item.materials }}</p>
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
  components: {
    HeaderComponent,
    FooterComponent
  },

  data() {
    return {
      services: [
        { 
          title: 'Convites Personalizados', 
          code: '001', 
          description: 'Personalizamos os convites para seu evento especial do jeito que quiser.',
          materials: 'Papéis personalizados, Envelopes decorados, Etiquetas adesivas, Fitas e Laços, Carimbos personalizados.',
          image: 'https://i.pinimg.com/564x/c8/20/5c/c8205c4b409ec64762a580d04d736697.jpg' // Link para a imagem do serviço
        },
        { 
          title: 'Planejadores e Agendas', 
          code: '002', 
          description: 'Crie planejadores e agendas personalizados para organizar seu ano com estilo.',
          materials: 'Cadernos com capa personalizada, Marcadores de página, Adesivos decorativos, Canetas coloridas, Régua.',
          image: 'https://i.pinimg.com/564x/8a/c9/52/8ac952739a482ea372c76457a6fe65c4.jpg' // Link para a imagem do serviço
        },
        { 
          title: 'Rótulos e Etiquetas', 
          code: '003', 
          description: 'Produzimos rótulos e etiquetas para qualquer necessidade, com designs únicos.',
          materials: 'Papéis adesivos, Impressão personalizada, Cortes especiais, Laminados protetores.',
          image: 'https://i.pinimg.com/564x/ac/36/ac/ac36ace09a4c5340d07896fae5437316.jpg' // Link para a imagem do serviço
        },
        { 
          title: 'Cartões de Visita', 
          code: '004', 
          description: 'Desenvolvemos cartões de visita profissionais que refletem sua marca.',
          materials: 'Papéis de alta gramatura, Acabamento fosco ou brilhante, Laminação, Corte personalizado.',
          image: 'https://i.pinimg.com/564x/74/f1/8f/74f18f9da2ad8d5d53f26155df9103f1.jpg' // Link para a imagem do serviço
        },
        { 
          title: 'Brindes Personalizados', 
          code: '005', 
          description: 'Oferecemos uma ampla gama de brindes personalizados para eventos e campanhas.',
          materials: 'Canecas, Canetas, Blocos de anotações, Bolsas, Pendrives, Etiquetas personalizadas.',
          image: 'https://i.pinimg.com/736x/2f/1f/13/2f1f13e3c59e9034c375b6ca943961b0.jpg' // Link para a imagem do serviço
        }
      ]
    };
  }
}
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.container-selecao-title {
  font-size: 24px;
  margin-bottom: 20px;
  color: #720372;
  text-align: center;
  font-weight: 600;
  justify-content: center;
}

.containerDisciplina {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 30px;
  max-width: 1100px;
  margin: 20px auto;
}

.services-container {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.service-container {
  display: flex;
  align-items: center;
  background-color: rgba(255, 255, 0, 0.103);
  border-radius: 8px;
  box-shadow: 0 0 10px  #4002462f;
  padding: 20px;
}

.service-left {
  flex: 1;
}

.service-square {
  width: 350px;
  height: 150px;
  background-color: #ede9ee;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  font-size: 18px;
  text-align: center;
  position: relative;
}

.service-image {
  width: 350px; /* Controla o tamanho da imagem */
  height: 150px; /* Controla o tamanho da imagem */
  /* object-fit: contain; /* Garante que a imagem seja ajustada proporcionalmente */
  position: absolute;
  border-radius: 10px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.service-right {
  flex: 2;
  padding-left: 20px;
}

.service-right h3 {
  font-size: 18px;
  margin-bottom: 10px;
}

.service-right p {
  margin: 5px 0;
}
</style>
