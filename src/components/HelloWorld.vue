<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
      <h2> {{ saludo }} </h2>
    <p> Mensaje original: {{ mensaje }}</p>
    <p> Mensaje al revés: {{ mensajeAlReves }}</p>
    <p> Mensaje al revés con Método sin trampa: {{ mensajeAlRevesConMetodoSinTrampa() }} </p>
    <p> Mensaje al revés con Método: <span id="unMensaje"></span></p> <button v-on:click="mensajeAlRevesConMetodo"> llamar metodo </button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
        mensaje: 'hola mundo otra vez',
        saludo: 'Bienvenidos',
    }//Fin return
  }, //fin data
  computed:{
    mensajeAlReves(){
      return this.mensaje.split('').reverse().join('')
    }//Fin mensajeAlReves
  }, //Fin Computed
  methods:{
       mensajeAlRevesConMetodoSinTrampa(){
          return this.mensaje.split('').reverse().join('');
       },
      mensajeAlRevesConMetodo(){
            let elMensajeAlReves = this.mensaje.split('').reverse().join('');
            let elSpan = document.getElementById('unMensaje');
            elSpan.innerHTML = elMensajeAlReves;
      }
  }, //fin methods
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
