<script setup>
    const pokemon = defineProps(["name"])
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3">
            <p class="text-center">{{ pokemon.name }}</p>
            <img src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/025.png" class="card-img-top" alt="...">
        </div>
    </div>
</template>

<style>

</style>