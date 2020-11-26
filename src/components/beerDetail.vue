<template>
    <div v-if="beer">
        <h3>{{beer.name}}</h3>
        <p>{{beer.tagline}}</p>
        <p>{{beer.abv}}</p>
        <img id="beer-img" :src="beer.image_url">
    </div>
</template>

<script>

// import {eventBus} from '../main.js'

export default {
    name: 'beer-detail',
    props: ['beer']
}
</script>

<style>
    #beer-img {
        width: 120px;
    }
</style>