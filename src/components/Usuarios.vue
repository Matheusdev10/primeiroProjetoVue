<script setup>

// defineProps({
//   count: Number
// })
const usuarios= ["Matheus", "yago"]
// const usuarios = new Vue({
//   el: '#example-1',

// })
</script>


<template>

<ul class="bg-primary" id="example-1">
  <li v-for="usuario in usuarios" :key="usuarios">
    {{ usuario }}
  </li>
</ul>
    
</template>

