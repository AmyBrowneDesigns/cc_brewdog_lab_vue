<template>
<div class="fave-beer-item">
  <div id="beer-text">
    <li>{{ beer.name }}</li>
    <img class="small-beer" :src="beer.image_url" alt="beer">
  </div>
  <button class='delete-button' v-on:click="handleClick" :value='beer'>Delete</button>
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
  .fave-beer-item {
    display: flex;
    flex-direction: column;
    border: 1px solid;
    padding: 20px;
    margin: 20px;
    border-radius: 25px;
    width: 80px;
    background-color: rgb(240, 107, 59);
  }

  #beer-text {
      margin: 10px;
      padding: 5px;
  }

  .delete-button {
      
  }

</style>