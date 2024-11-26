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
    <router-link to="/about">About</router-link> |
    <router-link to="/services">Service</router-link>
  </nav>

  <div class="center">
    <img alt="Vue logo" src="./assets/logo.png">
  </div>

  <router-view/>

</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader.vue'
import BaseAlert from './components/BaseAlert.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    TheHeader,
    BaseAlert
  },
  data() {
    return {
      showHeader: true,
    }
  },
  methods: {
    escondeHeader() {
      this.showHeader = !this.showHeader;
    },
    fechaAlert() {
                                                                                                                                       
    }
  },
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
