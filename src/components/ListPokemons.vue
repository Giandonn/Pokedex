<script setup>
    const pokemon = defineProps(["name"])
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3">
            <p>{{ pokemon.name }}</p>
        </div>
    </div>
</template>

<style>

</style>