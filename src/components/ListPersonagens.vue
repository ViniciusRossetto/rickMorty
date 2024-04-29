<script setup>
const personagem = defineProps(["name", "url", "specie","gender","status","location","episode"])
const personagemId = personagem.url.split('/')[5]
const imageUrl = "https://rickandmortyapi.com/api/character/avatar/" + personagemId + ".jpeg"
console.log(imageUrl)

</script>

<template>
  <div class="col-md-4">
    <div class="card p-2 mb-3">
      <img :src="imageUrl" height="280" alt="">
      <p class="text-center">{{personagem.name}}</p>
      <p class="text-center">{{personagem.specie}}</p>
      <p class="text-center">{{personagem.gender}}</p>
      <p class="text-center">{{personagem.status}}</p>
      <p class="text-center">{{personagem.location.name}}</p>
      <p class="text-center"> Aparições: {{personagem.episode.length}}</p>
    </div>
  </div>
</template>

<style>

</style>