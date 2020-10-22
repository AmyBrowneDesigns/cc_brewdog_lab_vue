<template>
<div>
  <h1>Brewdog List</h1>

</div>
  
</template>

<script>
export default {
  name:'App',
  data() {
    return {
      beers:[]
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
