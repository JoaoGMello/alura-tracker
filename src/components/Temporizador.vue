<template>
  <section class="is-flex is-align-items-center is-justify-content-space-between">
    <Cronometro :segundos="segundos"/>
    <Botao @clicado="iniciar" icone="fas fa-play" texto="play" :desabilitado="habilitado" />
    <Botao @clicado="finalizar" icone="fas fa-stop" texto="stop" :desabilitado="!habilitado" />
  </section>
</template>

<script lang="ts">
/* eslint-disable */
import { defineComponent } from 'vue';
import Cronometro from './Cronometro.vue';
import Botao from './Botao.vue';
export default defineComponent({
  name: 'Temporizador',
  emits:['aoTemporizadorFinalizado'],
  components: {
    Cronometro,
    Botao
  },
  data() {
    return {
      segundos: 0,
      cronometro: 0,
      habilitado: false
    }
  },
  methods: {
    iniciar() {
      this.habilitado = true
      this.cronometro = setInterval(() => {
        this.segundos += 1
      }, 1000)
    },
    finalizar() {
      this.habilitado = false
      clearInterval(this.cronometro)
      this.$emit('aoTemporizadorFinalizado', this.segundos)
      this.segundos = 0
    }
  }
});
</script>