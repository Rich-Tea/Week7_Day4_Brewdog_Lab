<template>
  <div v-if='beer'>
                <p><span>Name</span>: {{ beer.name }} </p>
                <p><span>Tagline</span>: {{beer.tagline }}  </p>
                <p><span>Description</span>: {{beer.description }}  </p>
                <p><span>Alcohol Content</span>: {{beer.abv }}  </p>
                <button type="submit" v-on:click="handleFavClick">Add to favourites </button>
    </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'beer-detail',
    props: ['beer'],
     data(){
        return {
            fav_beers: []
        };
    },
    methods: {
        handleFavClick() {
            this.fav_beers.push(this.beer)
            eventBus.$emit('fav-selected', this.selectedBeer)
        }
    }
}

</script>

<style>

</style>