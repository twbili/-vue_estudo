<template>
  <div>
    <button style="margin-bottom: 20px;" @click="escondeHeader">
      TESTE
    </button>
  </div>
  
  
  <TheHeader title="HEADER" v-show="showHeader">Teste</TheHeader>
  <BaseAlert close="fechaAlert()" variant="success" title="ALERT" v-if="showHeader">O HEADER ESTA ATIVO</BaseAlert>
  <BaseAlert close="fechaAlert()" variant="danger" title="ALERT" v-else>O HEADER ESTA DESATIVADO</BaseAlert>
  
  <div class="center">
    <img alt="Vue logo" src="./assets/logo.png">
    <input v-model="name" type="text">
  </div>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  
  <h1>Lista completada</h1>
  <div v-for ="(obj,index) in listaCompletada" :key="obj.id" class="for">
    <img :src="obj.imgSrc" alt="https://picsum.photos/200/300?random=n">
    <div class="text-center">
      {{index}}: {{ obj.title }}
    </div>
  </div>
  <br>
  <h1>Lista não completada</h1>
  <div v-for ="(obj,index) in listaNaoCompletada" :key="obj.id" class="for">
    <img :src="obj.imgSrc" alt="https://picsum.photos/200/300?random=n">
    <div class="text-center">
      {{index}}: {{ obj.title }}
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
  data(){
    return{
      showHeader: true,
      lista: [{
        "userId": 1,
        "id": 1,
        "title": "delectus aut autem",
        "completed": false,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 2,
        "title": "quis ut nam facilis et officia qui",
        "completed": false,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 3,
        "title": "fugiat veniam minus",
        "completed": false,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 4,
        "title": "et porro tempora",
        "completed": true,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 5,
        "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
        "completed": false,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 6,
        "title": "qui ullam ratione quibusdam voluptatem quia omnis",
        "completed": false,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 7,
        "title": "illo expedita consequatur quia in",
        "completed": false,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 8,
        "title": "quo adipisci enim quam ut ab",
        "completed": true,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 9,
        "title": "molestiae perspiciatis ipsa",
        "completed": false,
        "imgSrc": "https://picsum.photos/200/300?random=n"
    },
    {
        "userId": 1,
        "id": 10,
        "title": "illo est ratione doloremque quia maiores aut",
        "completed": true,
        "imgSrc": "https://picsum.photos/200/300?random=n"
      }]
    }
  },
  methods:{
    escondeHeader() {
      this.showHeader = !this.showHeader;
    }
  },
  computed:{
    listaCompletada(){
      return this.lista.filter(lista => lista.completed);
    },
    listaNaoCompletada(){
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
.for{font-family: Avenir, Helvetica, Arial, sans-serif;
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
  text-align: center; /* Caso queira centralizar também o texto dentro do input */
}
</style>
