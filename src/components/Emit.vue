<template>
    <h2>
    {{ foodName }}
    <img src="../assets/images/img_quality.svg" v-show="foodIsFavorite">
    </h2>
    <p>{{ foodDesc }}</p>
    <button @click="toggleFavorite">즐겨찾기</button>
</template>

<script>
export default {
    props:['foodName', 'foodDesc', 'isFavorite'],
    data() {
        return {
            foodIsFavorite: this.isFavorite
            }
    },
    methods: {
        toggleFavorite() {
            this.$emit('toggle-favorite');
        }
    }
}
</script>

<style>
    img{
        height: 1.5em;
        float: right;
    }
</style>