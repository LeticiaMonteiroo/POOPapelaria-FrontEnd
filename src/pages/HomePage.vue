<template>
    <HeaderComponent/>

<div class="informacao">
    <h2 class="text">Seu espaço para encontrar as ferramentas que trazem suas ideias à vida!</h2>
</div>

<div id="foto">
    <img src="../assets/ImagemTela1.png">
</div>

    <div class="Espaço">
        Espaço
    </div>
        
    <div id="servico">
        <div class="container">
            <h1> Destaques </h1>

            <div class="content">
                <div class="card">
                    <h2>Variedade</h2>
                    <p>
                        Descubra nossa ampla variedade de produtos que cobre todas as suas necessidades de papelaria. 
                        Desde itens de escritório até materiais escolares, garantimos opções para todos os gostos e demandas.
                    </p>
                </div>
                <div class="card">
                    <h2>Atendimento e Entrega Rápida</h2>
                    <p>
                        Com nosso atendimento online ágil e eficiente, você pode fazer suas compras com facilidade, 
                        enquanto nossa entrega rápida assegura que seus pedidos cheguem até você no menor tempo possível.
                    </p>
                </div>
                <div class="card">
                    <h2>Novidades e Tendências</h2>
                    <p>
                        Fique à frente com nossa seleção de novidades e tendências, trazendo os produtos mais inovadores e 
                        estilosos para que você sempre encontre o que há de mais atual no mercado.
                    </p>
                </div>
            </div>
        </div>
    </div>

    <div id="comunidade">
        <h1 class="titulo">Categorias</h1>
        <div id="habilidades">
            <div class="cartao">
                <h1>Material Escolar</h1>
            </div>
            <div class="cartao">
                <h1>Material de Impressão</h1>
            </div>
            <div class="cartao">
                <h1>Material de Escritório</h1>
            </div>
            <!-- Adicione outras categorias conforme necessário -->
        </div>
    </div>

    <div id="configuracoes">
        <div class="container2">
            <h1>Mais Vendidos</h1>
            <div class="Espaço1"></div>
            <div class="content2">
                <div class="card1">
                    <h2>Produto 1</h2>
                    <p>
                         
                    </p>
                </div>
                <div class="card1">
                    <h2>Produto 2</h2>
                    <p>
                    </p>
                </div>
                <div class="card1">
                    <h2>Produto 3</h2>
                    <p>
                    </p>
                </div>
            </div>
        </div>
    </div>


     <div class="Espaço">
        Espaço
     </div>

    <FooterComponent/>
</template>

<script>
import HeaderComponent from '../components/HeaderComponent.vue';
import FooterComponent from '../components/FooterComponent.vue';
export default {
    name: 'HomePage',

    components: {
        HeaderComponent,
        FooterComponent
    },
    data() {
        return {};
    },
}
</script>

<style>

.informacao {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 100px;
}

.text {
    align-items: center;
}



.container {
    width: 100%;
    min-height: 100vh; /* Garantir que a altura mínima seja 100% da altura da viewport */
    padding: 100px 0;
    background-color: #cb6ce6;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #f4d016;
}

.Espaço{
    width: 5%;
    min-height: 5vh; /* Garantir que a altura mínima seja 100% da altura da viewport */
    padding: 100px 0;
    color: #ffffff;
}

.Espaço1{
    width: 1%;
    min-height: 2vh; /* Garantir que a altura mínima seja 100% da altura da viewport */
    padding: 50px 0;
    color: #ffffff;
}

.container2 {
    width: 100%;
    min-height: 100vh; /* Garantir que a altura mínima seja 100% da altura da viewport */
    padding: 100px 0;
    background-color: #f3da5d;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color:  #cb6ce6;
}

.content {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.content2 {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.card {
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 2px 6px #545558;
    padding: 20px;
    text-align: center;
    margin: 10px;
    display: flex;
    flex-direction: column;
    width: 300px;
    align-items: center;
}

.card1 {
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 2px 6px #545558;
    padding: 20px;
    text-align: center;
    margin: 10px;
    display: flex;
    flex-direction: column;
    width: 300px;
    align-items: center;
}

.card h2 {
    margin-top: 12px;
    color: #720372;
}

.card p {
    margin-top: 10px;
    margin-bottom: 2px;
    color: #10162F;
}

.card1 h2 {
    margin-top: 12px;
    color: #720372;
}

.card1 p {
    margin-top: 10px;
    margin-bottom: 2px;
    color: #10162F;
}



#sobre h2 {
    margin-top: -350px;
    width: 1158px;
    height: 300px;
    text-align: center;
    font-size: 60px;
    font-weight: 700;
    line-height: normal;
    color: #cb6ce6;
}

.azul {
    color: #720372;
}

#foto {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100px;
}

#foto img {
    height: 100px;

    overflow-x: hidden;
}

#comunidade {
    padding-top: 50px;
    color: #720372;
}

#comunidade h1.titulo {
    font-size: 45px;
    font-weight: 150px;
    text-align: center;
    line-height: 45px;
    margin-top: 60px;
    margin-bottom: 80px;
    color: #f4d016;
}

#habilidades {
    padding-bottom: 100px;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

.cartao {
    margin: 0 30px;
    background-color: #e3e4e8;
    border-radius: 10px;
    padding: 30px;
    text-align: justify;
    margin-bottom: 30px;
    display: flex;
    flex-direction: column;
    height: 300px;
    width: 250px;
    justify-content: center;
    align-items: center;
    border: 2px solid #ffffff;
}

.cartao h1 {
    color: #161C2D;
    font-size: 16.336px;
    line-height: 17px;
    font-weight: 400;
    padding-top: 20px;
}

#msg {
    display: flex;
    flex-direction: column;
    gap: 10px;
    color: #ffffff;
}

#msg xmp {
    line-height: 39px;
    font-size: 26px;
    letter-spacing: 3px;
}

#msg h2 {
    font-weight: 400;
    font-size: 18px;
    line-height: 21px;
}

#contatos {
    display: flex;
    flex-direction: column;
    width: auto;
    gap: 20px;
    padding: 30px;
}

#contatos h1 {
    font-weight: 700;
    font-size: 30px;
    line-height: 34px;
    color: #0a0500;
}

#contatos ul {
    display: flex;
    justify-content: space-between;
    flex-flow: column wrap;
    list-style-type: none;
    gap: 20px;
}

#contatos li {
    display: flex;
    align-items: center;
    gap: 10px;
    background-color: pink;
}

#contatos a {
    text-decoration: none;
    font-weight: 400;
    font-size: 18px;
    line-height: 25px;
    color: #10162F;
}

#contatos a:hover {
    text-decoration: underline;
}

#contatos img {
    width: 27px;
    height: 25px;
}
</style>
