<script>

export default {
  data() {
    return {
      myLang: "python",
      inputvalue1: "python2",
      inputvalue2: "python3",
      count: 0,
    }
  },

  created() {
    this.myLang = "java";
  },


  // computed는 종속된 반응형 데이터가 변경될 때만 함수를 다시 실행하여 값을 계산하는 계산함수다.
  computed: {
    doubleCount(){
      return this.count *2;
    }
  },

  methods: {

    increment() {
      this.count++;
    },

    showValue(){
      alert(this.inputvalue2);
    }
  }
}
</script>


<template>
  <h1>Hello World {{myLang}}</h1>
  <input type="text" value="myvalue"/>

  <!--  :value는 v-bind:value= 의 축약어 -->
  <!--  v-bind는 input 박스에서 많이 사용하는 단방향 데이터 바인딩 방식 -->
  <input type="text" v-bind:value="inputvalue1"/>
  <input type="text" :value="inputvalue1"/>


  <!--v-model = 양방향 데이터 바인딩 모델이라는 차이점 -->
  <input type="text" v-model="inputvalue2"/>


<!--  oneclick = @click 와 간다. -->
  <button @click="showValue"> 변수 변경사항 확인 </button>

  <div>
    <h2>{{count}}</h2>
    <button @click="increment">increment</button>
  </div>
  <div>
    <h2>{{doubleCount}}</h2>
    <button @click="doubleCount">doublex2</button>
  </div>

</template>
