<template>
  <div class="jogo">
    <div class="title">
      <h1>Pedra Papel Tesoura</h1>
      <h2>Utilizador Computador</h2>
    </div>
    <div class="imagens">
      <div class="img">
        <Imagens :imagem="escolhaUser"/>
      </div>
      <div class="img">
        <Imagens :imagem="escolhaPc"/>
      </div>
    </div>
    <div class="pontuacao">
      <Pontuacao :pontuacaoUser="pontuacaoUser" :pontuacaoMach="pontuacaoMach"/> 
    </div>
    <div class="butoes">
      <div class="pedra">
        <Butoes opcao="pedra" v-on:escolhido="opcaoEscolhida"          />
      </div>

      <div class="papel">
        <Butoes opcao="papel" v-on:escolhido="opcaoEscolhida"          />
      </div>

      <div class="tesoura">
        <Butoes opcao="tesoura" v-on:escolhido="opcaoEscolhida"        />
      </div>

    </div>
  </div>
</template>

<script>
import Butoes from './components/Butoes';
import Pontuacao from './components/Pontuacao';
import Imagens from './components/Imagens';

export default {
  name: 'App',
  components: {
    Butoes,
    Pontuacao,
    Imagens
  },
  methods: {
      opcaoEscolhida(value){
        // Atribui a escolha enviada do filho na variavel escolhaUser
        this.escolhaUser = value;
        // Defenicao das escolha possiveis
        const possibilidades = ['Pedra', 'Papel', 'Tesoura'];
        // Geracao de uma escolha aleatoria por parte do pc
        this.escolhaPc = possibilidades[Math.floor(Math.random() * possibilidades.length)]; 
        this.atualizaResultado();
      },
      atualizaResultado: function () {
        if (this.escolhaUser === 'Pedra') {
          if (this.escolhaPc === 'Papel') {
            this.pontuacaoMach++;
          } else if (this.escolhaPc === 'Tesoura') {
            this.pontuacaoUser++;
          }

        } else if (this.escolhaUser === 'Papel') {
          if (this.escolhaPc === 'Pedra') {
            this.pontuacaoUser++;
          } else if (this.escolhaPc === 'Tesoura') {
            this.pontuacaoMach++;
          }

        } else {
          if (this.escolhaPc === 'Pedra') {
            this.pontuacaoMach++;
          } else if (this.escolhaPc === 'Papel') {
            this.pontuacaoUser++;
          }
        }
      }
    },
  data: function () {
    return {
      escolhaUser: null,
      escolhaPc: null,
      pontuacaoUser: 0,
      pontuacaoMach: 0
    };
  },
}
</script>

<style scoped>

.title{
  text-align: center; 
}
.title h2{
  word-spacing: 35px;
}
.imagens {
  margin-top: 110px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.img {
  width: 20%;
  padding: 10px;
}
.pontuacao {
  align-items: center;
  justify-content: center;
  display: flex;
}

.butoes {
  display: flex;
  align-items: center;
  justify-content: center;
}

.butoes .pedra{
  width: 7%;
}
.butoes .papel{
  width: 7%;
}
.butoes .tesoura{
  width: 7%;
}
</style>