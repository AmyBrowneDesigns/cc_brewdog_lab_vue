<template>
  <div id="favourite-beers">
      <h2>Favourite Beers</h2>
      <ul id="favourite-beers-list">
          <favourite-beer-list-item v-for="(favouriteBeer, index) in favouriteBeers" :key='index' :beer="favouriteBeer">{{ favouriteBeer.name }} 
          </favourite-beer-list-item>
      </ul>
      
  </div>
</template>

<script>
import { eventBus } from '../main.js';
import favouriteBeerListItem from './favouriteBeerListItem.vue';


export default {
    name: 'favourite-beers',
    props: ['favouriteBeers'],
    components: {
        'favourite-beer-list-item':favouriteBeerListItem
    }
    }

</script>

<style lang="css" scoped>

ul {
    list-style-type: none;
}

#favourite-beers-list {
    display: flex;
    flex-flow: row wrap;
}

</style>