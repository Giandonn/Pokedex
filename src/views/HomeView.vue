<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListPokemons from '../components/ListPokemons.vue'

let pokemons = reactive(ref())

onMounted (()=>{
  fetch("https://pokeapi.co/api/v2/pokemon?limit=20&offset=0")
  .then(response => response.json())
  .then(response => {
    pokemons.value = response.results
  });
})
</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
          <div class="card" style="width: 18rem;">
            <img src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/025.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Card Title</h5>
              <p class="card-text">Um texto resumido e pequeno</p>
            </div>
          </div>
        </div>
        <div class="col-sm-12 col-md-6">
          <div class="class" style="width: 18rem;">
            <ListPokemons
              v-for="pokemon in pokemons"
              :key="pokemon.name"
              :name="pokemon.name"
            />
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
