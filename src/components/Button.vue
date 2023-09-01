<script setup>
import Teste from './Teste.vue'
defineProps({
  count: Number
})

</script>


<template>
 <Teste v-bind:count="count"></Teste>
  <div class="card">
    <button type="button" v-on:click="count += 1">count is {{ count }}</button>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
