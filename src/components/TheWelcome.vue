<script setup>

</script>

<template>
  <h1>{{response}}</h1>

  <div class="projects">

  <ul v-for="(project,index) in AllProjects" :key="index">
  <li>{{project.title }}</li>
  <li>{{ project.category }}</li>
  <li>{{ project.description }}</li>
  <li>{{ project.price }}</li>
  <li>{{ project.language }}</li>
  </ul>
  

  </div>


<button @click="UserDetails">
click me
</button>
 
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      response:'Hatutaki!!',
      AllProjects:[]
    }
  },
methods: {
  UserDetails()
  {
    
    axios.get("fetch_all/project/")
    .then((res)=>{
      this.AllProjects=res.data.allProjects
    })



  }
},



}
</script>

<style scoped>
.projects ul
{
  display: flex;
  gap: .5rem;
  margin-bottom: .5rem;

  
}
.projects ul li
{
  padding: 6px;
  background-color: rebeccapurple;
  width: 10rem;
  list-style: none;
  text-align: center;
}


</style>
