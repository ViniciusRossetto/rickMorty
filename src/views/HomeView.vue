<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';

let personagens = reactive(ref());

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results
    console.log(personagens)
  })
})

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-12">
          <div class="card">
            <div class="card-body row">
              <ListPersonagens 
            v-for="personagem in personagens" 
            :key="personagem.name" 
            :name="personagem.name"
            :url="personagem.url"
            :specie="personagem.specie"
            :gender="personagem.gender"
            :status="personagem.status"
            :location="personagem.location"
            :episode="personagem.episode"
            />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
