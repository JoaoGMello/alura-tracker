<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input 
        type="text"
        class="input"
        placeholder="Qual tarefa voçê deseja iniciar?"
        v-model="descricao"
        >
      </div>
      <div class="column">
        <Temporizador @ao-temporizador-finalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
/* eslint-disable */
  import { defineComponent } from 'vue';
  import Temporizador from './Temporizador.vue';
  export default defineComponent({
    name: 'Formulario',
    components:{
      Temporizador
    },
    data() {
      return{
        descricao: '',
      }
    },
    methods:{
      finalizarTarefa(segundos: number) : void{
        console.log(segundos)
        console.log(this.descricao)
        this.descricao = ''
      }
    }
  });
</script>

<style scoped>

</style>