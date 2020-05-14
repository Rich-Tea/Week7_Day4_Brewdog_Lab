<template lang="html">
  <div class="main-container">
    <h1>Brewdog Beers</h1>
    <div class="main container">
      <beer-list :beers="beers"></beer-list>
      <beer-detail :beer="selectedBeer"></beer-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import BeerDetail from './components/BeerDetail.vue'
import BeerList from './components/BeerList.vue'

export default {
     name: 'app',
     data(){
       return {
         beers: [],
         selectedBeer: null
       };
     },
     components: {
       "beer-list": BeerList,
       "beer-detail": BeerDetail
     },
     mounted(){
       fetch('https://api.punkapi.com/v2/beers')
       .then(res => res.json())
       .then(beers => this.beers = beers)

       eventBus.$on('beer-selected', (beer) => {
         this.selectedBeer = beer
       })
     }
}
</script>

<style>
 

</style>