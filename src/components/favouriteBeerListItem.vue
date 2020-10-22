<template>
<div>
  <li>{{ beer.name }}</li>
  <img :class= "small-beer" :src="beer.image_url" alt="beer">
  <button v-on:click="handleClick" :value='beer'>
  Delete</button>
</div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
    name: 'beer-list-item',
    props: ['beer'],
    methods: {
    handleClick() {
        eventBus.$emit('beer-item', this.beer)        
    }
}
}
</script>

<style>

</style>