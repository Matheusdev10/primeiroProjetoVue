
<script setup>
import Button from './components/Button.vue'
import Usuarios from "./components/Usuarios.vue"
import Api from "./components/Api.vue"

import { ref } from 'vue'
const count = ref(10)
</script>

<template>
  <!-- <Usuarios></Usuarios>
  <Button v-bind:count="count"></Button> -->
  <Api></Api>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
