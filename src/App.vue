<template>
  <div>
    <h1>Beers</h1>
    <div class="main-container">
      <beers-list :beers='beers'></beers-list>
      <beer-detail :beer="selectedBeer"></beer-detail>
      
    </div>
    <button v-on:click="addToFav">Add to favourites</button>
    <favourite-beers :favouriteBeers="favouriteBeers"></favourite-beers>
  </div>
</template>

<script>

import beersList from './components/beersList.vue';
import beerDetail from './components/beerDetail.vue';
import { eventBus } from './main';
import favouriteBeers from './components/favouriteBeers.vue'


export default {
  name: 'app',
  data(){
    return {
      beers: [],
      selectedBeer: null,
      favouriteBeers: []
    };
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(result => result.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer
    })
  },
  components: {
    'beers-list': beersList,
    'beer-detail': beerDetail,
    'favourite-beers': favouriteBeers
  },
  methods: {
    addToFav: function(){
      this.favouriteBeers.push(this.selectedBeer)
    }
    }
  };

</script>

<style>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>
