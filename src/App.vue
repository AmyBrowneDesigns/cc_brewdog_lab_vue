<template lang="html">
<div>
  <h1>Brewdog List</h1> 
  <label for="select_beer">Select a Beer</label>
  <select id="select_beer" v-model='selectedBeer'>
    <option disabled selected value="">Select a Beer</option>
    <option v-for="beer in beers" :key="beer.id" :value="beer">{{beer.name}}</option>
  </select>

<beer-detail v-if="selectedBeer" :selectedBeer="selectedBeer"></beer-detail>

<button v-if="!favouriteBeers.includes(selectedBeer)" v-on:click="addToFavourites">Add beer to your favourites!
</button>

<favourite-beers :favouriteBeers="favouriteBeers">
  </favourite-beers>

</div>
  
</template>

<script>
import BeerDetail from './components/BeerDetail.vue';
import FavouriteBeer from './components/FavouriteBeer.vue';

export default {
  name:'App',
  data() {
    return {
      beers:[],
      selectedBeer:null,
      favouriteBeers: []
    }
  },
  mounted(){
    this.getBeers()
  },

  methods:{
    getBeers:function() {
      fetch('https://api.punkapi.com/v2/beers/')
      .then(res => res.json())
      .then(beers => this.beers = beers)
    },
    addToFavourites: function() {
      this.favouriteBeers.push(this.selectedBeer)
    }
  },

  components: {
    'beer-detail': BeerDetail,
    'favourite-beers': FavouriteBeer
  }

  }

</script>

<style>
.small-beer {
  height: 80px;
}

</style>
