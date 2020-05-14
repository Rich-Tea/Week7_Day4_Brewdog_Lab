<template>
  <div v-if='beer'>
                <p><span>Name</span>: {{ beer.name }} </p>
                <p><span>Tagline</span>: {{beer.tagline }}  </p>
                <p><span>Description</span>: {{beer.description }}  </p>
                <p><span>Alcohol Content</span>: {{beer.abv }}  </p>
    </div>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['beer']
}
</script>

<style>

</style>