<template>
    <div>
        <h2>Favourite Beers</h2>
        <ul>
            <li v-for="(beer, index) in favouriteBeers" :key="index" beer="beer">
                <span>{{beer.name}}</span>
                <button v-on:click="deleteBeer(index)">Remove</button>
                </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'favourite-beers',
    props: ['favouriteBeers'],
    methods: {
    deleteBeer: function(index) {
        this.favouriteBeers.splice(index, 1);
    }
    }
};
</script>

<style>
button {
    margin: 10px
}
</style>