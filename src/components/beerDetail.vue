<template>
    <div v-if="beer">
        <h3>Name: {{beer.name}}</h3>
        <p>Tagline: {{beer.tagline}}</p>
        <p>Alcohol by Volume: {{beer.abv}}</p>
        <img id="beer-img" :src="beer.image_url">
        <!-- <p ingredients="getIngredients(beer)">Malt: {{ingredientsList}} </p> -->
        <p>Malt: {{maltList}}</p>
        <p>Hops: {{beer.ingredients.hops}}</p>
        <p>Yeast: {{beer.ingredients.yeast}}</p>
    </div>
</template>

<script>

// import {eventBus} from '../main.js'

export default {
    name: 'beer-detail',
    props: ['beer', 'beers'],

    data() {
        return {
            maltList: []
        }
    },

    computed: {

        getMalt: function(beer) {
            for (malt in beer.ingredients.malt);
            this.maltList.push(malt.name);
            return maltList
        }
        
        // getIngredients: function(beer) {
        //     ingredientsList: [];
        //     for (beer.ingredients in beer);
        //     this.ingredientsList.push(ingredients.malt.name, ingredients.hops.name, ingredients.yeast.name);
        // return this.ingredientsList
        // }
    }
}
</script>

<style>
    #beer-img {
        width: 120px;
    }
</style>