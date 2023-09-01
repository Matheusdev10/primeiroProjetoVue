
<script>
  import api from "./api";

  export default {
   name: "Repos",
   data() {
     return {
       repos: [],
     };
   },
   created() {
     this.getRepos();
   },
   methods: {
     getRepos() {
       api
         .get("users/matheusdev10/repos")
         .then((res) => {
            console.log(res.data);
           this.repos = res.data;
         })
         .catch((error) => {
           console.log(error);
         });
     },
   },
  };

  let id = ""
  let node_id = ""
  let name = ""
  let full_name = ""
</script>
<template>
      <table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Id</th>
      <th scope="col">Node Id</th>
      <th scope="col">Nome</th>
      <th scope="col">Nome Completo</th>
    </tr>
  </thead>
  <tbody>
    <tr  v-for="(repo, index) in repos" :key="repo.name">
      <th scope="row">{{ index+1 }}</th>
      <td>{{repo.id}}</td>
      <td>{{ repo.node_id }}</td>
      <td>{{ repo.name }}</td>
      <td>{{ repo.full_name }}</td>
      <button @click='repos = repos.filter((r)=>r.id !== repo.id)' type="button" class="btn btn-danger">Excluir</button>
    </tr>
  </tbody>
</table>


<form >
<input :value="id" placeholder="digite o id" @input="event=>id=event.target.value">
<input :value="node_id" placeholder="digite o node_id" @input="event=>node_id=event.target.value">
<input :value="name" placeholder="digite o nome" @input="event=>name=event.target.value">
<input :value="full_name" placeholder="digite o full_name" @input="event=>full_name=event.target.value">


<button @click="repos.push({id, node_id, name, full_name})" type="button" class="btn btn-primary">Adicionar item</button>
</form>




</template>



<style scoped>
.read-the-docs {
  color: #888;
}
</style>
