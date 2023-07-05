<template>
  <div class="box has-text-weight-bold">
    <slot></slot>
  </div>
</template>

<script lang="ts">
/* eslint-disable */
import { defineComponent } from 'vue';

export default defineComponent ({
name: 'Box',

});
</script>

<style scoped>
.box{
  background-color: #FAF0CA;
}
</style>