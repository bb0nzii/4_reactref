<!--
vue 구성요소 : 사용자의 인터페이스와 특정부분을 캡슐화하는 재사용 가능하고 독립적인 코드 조각으로 사용하는 것
-->

<template>
  <div v-on:click="conutClicks">
    <h1>{{foodName}}</h1>
    <img src="../assets/images/img_quality.svg" v-show="isFavorite">
    <p>{{foodDesc}}</p>
    <h2>{{name}}</h2>
    <p>{{message}}</p>
    <p id="red">
        저를 {{clicks}}번 클릭하셨네요!
    </p>
  </div>
</template>

<script>
export default {
    data(){
        return{
            name: '뽄지',
            message: '물만두만두만두',
            clicks: 0
        }
    },
    methods:{
        conutClicks(){
            this.clicks++
            //++은 증가, --은 감소
        }
    },
    props:[
        'foodName', 'foodDesc', 'isFavorite'
    ]
}
</script>

<style>
    #red{
        font-weight: bold;
        color: rgb(144, 12, 12);
    }
    img{
        height: 1.5em;
        float: right;
    }
</style>