<script setup>
import { ref } from "vue";
import {useRouter} from "vue-router"
import monstersData from "../data.json"

const router = useRouter()
const monsters = ref(monstersData);
</script>

<template>
  <main class="container">
    
    <h1>Monster Logs</h1>
    <div class="cards">
      <div v-for="monster in monsters" :key = monster.id class="card" @click="router.push(`/monster/${monster.id}`)">
      <h2>{{ monster.name }}</h2>
      <p>Gen:{{monster.gen}}</p>
      <img :src="monster.img">
      </div>
    </div>

  
  </main>
</template>

<style scoped>
.cards {
  display: flex;
  width: 800px;
  flex-wrap: wrap;
  margin-top: 50px;
  justify-content: center;
  justify-content: space-around;
}
h2{
    text-decoration: underline;
}
.card {
  box-shadow: 1px 1px 10px rgba(239, 237, 237, 0.207);
  padding: 15px;
  width: 250px;
  color: black;
  cursor: pointer;

  margin-bottom: 20px;
  background-color: rgb(255, 255, 255);
  

}

.card img{
  width:200px;
}

.links {
  padding: 20px
}

.links a {
  margin: 0 5px
}

</style>
