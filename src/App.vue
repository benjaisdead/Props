<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    {{ mensaje }}
    <button v-on:click="mensaje = 'hello world!!!'"> hola </button>
    <button v-on:click="destroy()"> Destruir </button>
    <HelloWorld msg="Mensaje del Padre"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return{
      mensaje: 'hola mundo !!!',
    }//Fin return
  }, //fin data
  beforeCreate(){
      console.log('beforeCreate: ', this.mensaje);
  },
  created(){
      console.log('created: ', this.mensaje);
  },
  beforeMount(){
      console.log('beforeMount: ', this.mensaje);
  },
  mounted(){
      console.log('mounted: ', this.mensaje);
  },
  beforeUpdate(){
     console.log('beforeUpdate: ', this.mensaje);
  },
  updated(){
    console.log('updated: ', this.mensaje);
  },
  beforeDestroy(){
    console.log('beforeDestroy: ', this.mensaje);
  },
  destroyed(){
    console.log('destroyed: ', this.mensaje);
  },
  methods:{
    destroy(){
        this.$destroy();
    }
  }
}//Fin export
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
</style>
