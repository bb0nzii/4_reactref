<!--
Vue $emit() 매소드
 => 구성요소에서 부모로 정보를 전송해야 하는 경우 사용(props의 반대)

- 부모요소에서 캡쳐할 수 있는 사용자 정의 이벤트를 자식 구성요소에서 만들 수 있음
- Props는 부모요소에서 자식구성요소로 데이터를 전송하는 데 사용
- 반대로 $emit()은 자식구성요소에서 부모요소에게 데이터를 전송하는 데 사용
-->

<template>
  <h1>에밋메서드</h1>
  <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptatem, cumque!</p>
  <div id="wrapper">
    <div>
    <food-item
    v-for="x in foods"
    :key="x.name"
    :food-name="x.name"
    :food-desc="x.desc"
    :is-favorite="x.favorite"
    @toggle-favorite="receiveEmit"
    />
    </div>
  </div>
</template>

<script>
export default{
  data(){
    return{
        foods:[
        { name: 'Apples', desc: 'Apples are a type of fruit that grow on trees.', favorite: true},
        { name: 'Pizza', desc: 'Pizza has a bread base with tomato sauce, cheese, and toppings on top.', favorite: false},
        { name: 'Rice', desc: 'Rice is a type of grain that people like to eat.', favorite: false},
        { name: 'Fish', desc: 'Fish is an animal that lives in water.', favorite: true},
        { name: 'Cake', desc: 'Cake is something sweet that tastes good.', favorite: false}
        ]
    }
  },
  methods:{
     receiveEmit(){
      alert("Hello World")
    }
  }
}
</script>

<style>
#wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  #wrapper > div {
    border: dashed black 1px;
    flex-basis: 120px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
</style>