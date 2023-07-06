<template>
  <header>
    <h1>
      <img src="../assets/logo.png" alt="">
    </h1>
    <button class="button" @click="alterarTema">
      {{ textoBotao }}
    </button>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'BarraLateral',
  
  emits:['aoTemaAlterado'],

  data(){
    return{
      temaEscuro: false,
    }
  },

  methods:{
    alterarTema(){
      this.temaEscuro = !this.temaEscuro
      this.$emit('aoTemaAlterado', this.temaEscuro)
    }
  },

  computed:{
    textoBotao(){
      if(this.temaEscuro){
        return "Tema Claro"
      }else{
        return "Tema Escuro"
      }
    }
  },
});
</script>

<style scoped>
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
  text-align: center;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>