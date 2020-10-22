<template lang="html">
<div>
  <h1>Brewdog List</h1> 
  <label for="select_beer">Select a Beer</label>
  <select id="select_beer" v-model='selectedBeer'>
    <option disabled value="">Select a Beer</option>
    <option v-for="beer in beers" :key="beer.id" :value="beer">{{beer.name}}</option>
  </select>

</div>
  
</template>

<script>
export default {
  name:'App',
  data() {
    return {
      beers:[],
      selectedBeer:null
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
    }
    }
  }

</script>

<style>

</style>
