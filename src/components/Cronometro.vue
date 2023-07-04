<template>
    <section>
      <strong>{{ tempoDecorrido }}</strong>
    </section>
</template>

<script lang="ts">
/* eslint-disable */
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Cronometro',
  props:{
    segundos:{
      type: Number,
      default: 0
    },
  },
  computed:{
      tempoDecorrido () : string {
        return new Date(this.segundos * 1000).toISOString().substr(11,8)
      }
    },
});
</script>