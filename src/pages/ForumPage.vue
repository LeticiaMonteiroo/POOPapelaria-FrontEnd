<template>
  <section>
    <HeaderComponent/>

    

    <!-- Conteúdo principal -->
    <div class="containerDisciplina">
      <!-- Container de serviços -->
      <div class="services-container">
        <div 
          v-for="item in services" 
          :key="item.code" 
          class="service-container"
        >
          <div class="service-left">
            <div class="service-square">
              <p>{{ item.title }}</p>
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
      showModal: true, // Controla a exibição do modal
      services: [
        { 
          title: 'Convites Personalizados', 
          code: '001', 
          description: 'Personalizamos os convites para seu evento especial do jeito que quiser.',
          materials: 'Papéis personalizados, Envelopes decorados, Etiquetas adesivas, Fitas e Laços, Carimbos personalizados.'
        },
        { 
          title: 'Planejadores e Agendas', 
          code: '002', 
          description: 'Crie planejadores e agendas personalizados para organizar seu ano com estilo.',
          materials: 'Cadernos com capa personalizada, Marcadores de página, Adesivos decorativos, Canetas coloridas, Régua.'
        },
        { 
          title: 'Rótulos e Etiquetas', 
          code: '003', 
          description: 'Produzimos rótulos e etiquetas para qualquer necessidade, com designs únicos.',
          materials: 'Papéis adesivos, Impressão personalizada, Cortes especiais, Laminados protetores.'
        },
        { 
          title: 'Cartões de Visita', 
          code: '004', 
          description: 'Desenvolvemos cartões de visita profissionais que refletem sua marca.',
          materials: 'Papéis de alta gramatura, Acabamento fosco ou brilhante, Laminação, Corte personalizado.'
        },
        { 
          title: 'Brindes Personalizados', 
          code: '005', 
          description: 'Oferecemos uma ampla gama de brindes personalizados para eventos e campanhas.',
          materials: 'Canecas, Canetas, Blocos de anotações, Bolsas, Pendrives, Etiquetas personalizadas.'
        },
      ]
    };
  },

  methods: {
    closeModal() {
      this.showModal = false;
    }
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

.modal {
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  text-align: center;
  max-width: 500px;
  width: 80%;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
}

.modal h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.modal p {
  font-size: 16px;
  margin-bottom: 20px;
}

.modal button {
  background-color: #cb6ce6;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

.modal button:hover {
  background-color: #720372;
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
  width: 150px;
  height: 150px;
  background-color: #cb6ce6;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  font-size: 18px;
  text-align: center;
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
