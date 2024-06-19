<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Cabe from './components/Cabecalho.vue'
import img from './assets/favicon.png'
</script>

<template>
  <div id="corpo">
    <div>
      <Cabe :logo="img"/>
    </div>
    <div class="tamanho">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
  #corpo {
    width: 100%;
  }
  .tamanho{
    align-items: center;
    margin: auto;
  }
</style>
