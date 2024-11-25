<template>
  <div>
    <button style="margin-bottom: 20px;" @click="escondeHeader">
      TESTE
    </button>
  </div>

  <TheHeader title="HEADER" v-show="showHeader">HEADER</TheHeader>
  <BaseAlert :close="fechaAlert" variant="success" title="ALERT" v-if="showHeader">O HEADER ESTA ATIVO</BaseAlert>
  <BaseAlert :close="fechaAlert" variant="danger" title="ALERT" v-else>O HEADER ESTA DESATIVADO</BaseAlert>

  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>

  <router-view/>

  <div class="center">
    <img alt="Vue logo" src="./assets/logo.png">
    <input v-model="name" type="text">
  </div>
  
  <HelloWorld msg="Welcome to Your Vue.js App"/>

  <h1>Lista completada</h1>
  <div v-for="(obj, index) in listaCompletada" :key="obj.id" class="todo-item">
    <img :src="obj.imgSrc" :alt="'Imagem do item ' + obj.title">
    <div class="text-center">
      {{ index }}: {{ obj.title }}
    </div>
  </div>
  <br>

  <h1>Lista não completada</h1>
  <div v-for="(obj, index) in listaNaoCompletada" :key="obj.id" class="todo-item">
    <img :src="obj.imgSrc" :alt="'Imagem do item ' + obj.title">
    <div class="text-center">
      {{ index }}: {{ obj.title }}
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader.vue'
import BaseAlert from './components/BaseAlert.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TheHeader,
    BaseAlert
  },
  data() {
    return {
      showHeader: true,
      lista: [ /* Sua lista de itens */ ]
    }
  },
  methods: {
    escondeHeader() {
      this.showHeader = !this.showHeader;
    },
    fechaAlert() {
      // Lógica para fechar o alerta
    }
  },
  computed: {
    listaCompletada() {
      return this.lista.filter(lista => lista.completed);
    },
    listaNaoCompletada() {
      return this.lista.filter(lista => !lista.completed);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.todo-item {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.center {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center; 
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
