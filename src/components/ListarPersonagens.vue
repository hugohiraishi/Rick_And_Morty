<script setup >
    const personagem = defineProps(["id","name","imagem","status", "species","gender","location", "episodeCount"])
    const imagem = "https://rickandmortyapi.com/api/character/avatar/" + personagem.id + ".jpeg";
</script>

<template>
    <div class="col-md-4 mb-3">
        <div class="card bg-dark">
            <div class="card-body d-flex align-items-center">
                <img :src="imagem" height="200" alt="Imagem do Personagem" class="me-3"> 
                <p class="text-white">
                    Nome: {{ personagem.name }}<br> 
                    Status: {{ personagem.status }}<br> 
                    Espécie: {{ personagem.species }}<br> 
                    Gênero: {{personagem.gender}}<br>
                    Localização: {{ personagem.location }}<br>
                    
                    <br>Apareceu em {{ episodeCount }} episódios
                </p>      
            </div>
        </div>
    </div>
  </template>
  


  