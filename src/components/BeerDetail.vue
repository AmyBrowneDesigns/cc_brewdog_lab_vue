<template>
    <div id="selected_beer">
        <h2>Beer name: {{ selectedBeer.name }}</h2>  
        <p>Tagline: {{ selectedBeer.tagline }}</p>
        <p>Description: {{ selectedBeer.description}}</p>
        <p>ABV: {{ selectedBeer.abv }}</p>
        <img class="beer-image" v-if="selectedBeer" :src="selectedBeer.image_url" alt="image_of_bottle" />
    </div>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['selectedBeer']
}
</script>

<style>
    .beer-image {
        max-height: 250px;
    }
</style>