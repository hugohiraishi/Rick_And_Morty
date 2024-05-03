<script setup>

import { onMounted, reactive, ref } from 'vue';
import ListarPersonagens from '../components/ListarPersonagens.vue'

let personagens = reactive(ref());

const getEpisodeCount = (episodes) => {
  return episodes.length;
};

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character?limit=20")
  .then(response => response.json())
  .then(response =>{
    personagens.value = response.results
    console.log(personagens)
  })
})

</script>


<template>
 <main>
  <div class="card">
    <div class="card-body">
      <div class="row">
        <ListarPersonagens
          v-for="personagem in personagens"
          :key="personagem.id"
          :id="personagem.id"
          :name="personagem.name"
          :imagem="personagem.imagem"
          :status="personagem.status"
          :species="personagem.species"
          :gender="personagem.gender"
          :location="personagem.location.name"
          :episodeCount="personagem.episode.length" 
        />
      </div>
    </div>
  </div>
</main>

</template>
