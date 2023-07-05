<template>
  <Box class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is -7">
        {{ tarefa.descricao || 'Tarefa sem descrição' }}
      </div>
      <div class="column">
        <Cronometro :segundos="tarefa.duracaoEmSegundos"/>
      </div>
    </div>
  </Box>
</template>

<script lang="ts">
/* eslint-disable */
import { PropType, defineComponent } from 'vue';
import Cronometro from './Cronometro.vue';
import ITarefa from '@/interfaces/ITarefa';
import Box from './Box.vue';

export default defineComponent ({
name: 'Tarefa',
components:{
  Cronometro,
  Box
},
props:{
  tarefa:{
    type: Object as PropType<ITarefa>,
    required: true
  }
},


});
</script>

<style scoped>

</style>