<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>


<template>
  <main>
    <div class="links">
      <h2>Monster Hunter Collection</h2>
      <RouterLink active-class="active" to="/">Home</RouterLink>
      <RouterLink active-class="active" to="/about">About</RouterLink>
    </div>
    <RouterView/>
  </main>
</template>

<style scoped>
.links{
  padding: 25px;
  background-color: black;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}

.links a{
  margin: 0 5px;
}

.links h2{
  color: white;
  margin-right: 250px;
}

.active{
  color:red;
  font-weight: bold;
}
</style>