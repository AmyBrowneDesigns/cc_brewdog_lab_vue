<template>
  <div id="favourite_beers">
      <h2>Favourite Beers</h2>
      <ul>
          <li v-for="favouriteBeer in favouriteBeers">{{ favouriteBeer.name }} <img class="small-beer" :src="favouriteBeer.image_url">
          </li>

      </ul>
  </div>
</template>

<script>
export default {
    name: 'favourite-beers',
    props: ['favouriteBeers']
}
</script>

<style lang="css" scoped>

</style>