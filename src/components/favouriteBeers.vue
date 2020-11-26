<template>
    <div>
        <h2>Favourite Beers</h2>
        <ul>
            <li v-for="(beer, index) in favouriteBeers" :key="index" beer="beer">{{beer.name}}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'favourite-beers',
    props: ['favouriteBeers']
}
</script>

<style>

</style>