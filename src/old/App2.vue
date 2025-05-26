

<template>
  <h1 class="mt-5 mb-3 fw-bold text-success">Food</h1>
  <p>아래에 버튼을 누르면 item이 순차적으로 하나씩 제거됩니다.</p>
  <button class="btn btn-outline-danger" @click="removeItem">Meow!</button>
  <div id="wrapper">
    <food-item 
    v-for = "x in foods" 
    :key="x.name"
    :food-name="x.name"
    :food-desc="x.desc"
    :is-favorite="x.favorite"
    />
    <!-- 아까는 수량대로 아이템을 적었는데 그러면 불편하니까 아이템을 컴포넌트 모듈화 시키고 필요한 만큼 재사용 -->
  </div>
</template>

<script>
export default{
  data(){
    return{
    foods:[
      {name:'사과', desc:'red', favorite:true},
      {name:'피자', desc:'orange', favorite:false},
      {name:'바나나', desc:'yellow', favorite:false},
      {name:'초콜릿', desc:'brown', favorite:true},
      {name:'케이크', desc:'white', favorite:false}
    ]
    }
  },
  methods:{
  removeItem(){
    this.foods.splice(1,1);   
  }
  }
}
</script>

<style>
  /* #app>div{
    border: dashed black 1px;
    display: inline-block;
    width: 400px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
  #app>div:hover{
    cursor: pointer;
  } */
   
   #wrapper{
    display: flex;
    flex-wrap: wrap;
   }
   #wrapper > div{
    border: dashed black;
    flex-basis: 120px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
   }
</style>

<!--
SFC : Single File Component
-->

<!--
20250515 v-for Component
: 동일한 종류의 많은 요소를 생성하는데 재사용될 수 있음
v-for 배열의 값에 따라 props를 동적으로 할당할 수 있음

Vue Props
-
  components: { FoodItem }, 뷰의 구성옵션
- props를 사용하면 사용자 정의 속성을 컴포넌트태그에 지정하여 컴포넌트에 데이터를 전달할 수 있음
- 구성 요소에 데이터 전달
- 리액트에서 클래스형 컴포넌트에서 최초 props를 사용함, 그리고 함수형 컴포넌트가 나오면서 props를 hook가 대체함. 근데 뷰는 아직 프롭스 씀
- 컴포넌트 태그를 만들고 props를 전달하는 예시를 아래에 구현
-->