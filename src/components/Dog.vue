<script>
import api from './api';

export default {
  name: 'Dogs',
  data() {
    return {
      dogs: [],
    };
  },
  created() {
    this.getDogs();
  },
  methods: {
    getDogs() {
      api
        .get(
          'https://api.thedogapi.com/v1/images/search?live_dkGSWyOwkYxc7oNgmzue4B8n9wZBqa3nciFoa2ajCX7Dn21vAOUJk9VrFS7tvyQV'
        )
        .then((res) => {
          console.log(res.data);
          this.dogs = res.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>
<template>
  <div class="d-flex flex-column" v-for="dog in dogs" :key="dog.id">
    <img :src="dog.url" :height="500" :width="500" />
    <div class="p-5">
      <button @click="getDogs()">clique para gerar um cão</button>
    </div>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>

<!-- <script>
const ola = 'matheus';
console.log(ola);
</script> -->
