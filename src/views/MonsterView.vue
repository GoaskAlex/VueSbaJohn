<script setup>
import {useRoute} from "vue-router"
import {ref, onBeforeMount} from "vue"
import monsters from "../data.json"
const route =useRoute()
const monster = ref (null)
const {id} = route.params

onBeforeMount(()=>{
    monster.value =monsters.find( monster=> monster.id == id)
})
console.log(route.params);
</script>

<template>
    <div class="description">
        <header>
        <h1>{{ monster.name }}</h1>
        </header>
        <div class="card">
        <img :src="monster.graphic"/>
        <ul class="stats">
            <li>{{ monster.weakness }}</li>
            <li>{{ monster.habitat }}</li>
        </ul> 
        </div>

        <div class="article">
            <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Odit animi earum sint, recusandae qui incidunt nobis cum labore amet dolores.</p>

        </div>

    </div>
    </template>

<style scoped>
.description{
    background-color: black;
    width:800px;
    padding:10px;
    margin: 0 auto;
    margin-top: 40px;
    color: white;
    display: flex;
    flex-wrap: wrap;
    border: white 5px groove;
}

header{
    padding: 15px;
    margin-bottom: 20px;
    width: 100%;
    text-decoration: underline;
    
}


.card{
    width: 50%;
    margin: 5px;
    padding: 10px;


}

.card img{
    width:300px;
    border: 2px solid white;

}

.stats{
    list-style: none;
}

.article{
    margin-top: 13px;

    border:white 3px solid;
    width:40%;

}
</style>