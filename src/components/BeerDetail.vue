<template>
    <div id="selected_beer">
        <div id="beer_details">
            <h2>Beer name: {{ selectedBeer.name }}</h2>  
            <p>Tagline: {{ selectedBeer.tagline }}</p>
            <p>Description: {{ selectedBeer.description}}</p>
            <p>ABV: {{ selectedBeer.abv }}</p>
        </div>
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
        padding: 10px;
    }

    #selected_beer {
        display: flex;
        flex-direction: row;
        box-sizing: border-box;
        height: 350px;
        width: 60%;
        background: whitesmoke;
        color: #222;
        padding: 10px;
        margin: 20px;
        border: 1px solid #ccc;
        border-radius: 15px;
    }

    #beer_details {
        padding: 10px;
        margin: 10px;
    }
</style>