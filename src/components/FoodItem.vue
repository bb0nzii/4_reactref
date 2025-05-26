<template>
  <h2>{{foodName}}</h2>
  <img src="../assets/images/stamp.svg" v-show="foodIsFavorite">
  <p>{{foodDesc}}</p>
  <button v-on:click.stop="toggleFavorite">Favorite</button>
</template>

<script>
export default {
    props:['foodName', 'foodDesc', 'isFavorite'],
    data(){
        return{
            foodIsFavorite: this.isFavorite
        }
    },
    methods:{
        toggleFavorite(){
            this.foodIsFavorite = !this.foodIsFavorite;
        }
    }
};
</script>

<style>
img{height: 1.5em; float: right;}
</style>