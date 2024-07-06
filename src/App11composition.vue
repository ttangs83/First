<template>
  <h2> App.vue문서 compositions API변환</h2>
  <img src="./assets/images/cake3.jpg" height="150" width="300">
  <p></p>
    <!--디저트 : {{ kind }}<br> -->
    안내문 : {{ info }}<br>
    <h3>카운트 : {{ count }}</h3><p></p>
    <button @click="increment">증가1</button> &nbsp;
    <button @click="decrement">감소1</button> &nbsp;
    <button v-on:click="increment">증가2</button> &nbsp;
    <button v-on:click="decrement">감소2</button>

  <hr color="blue" size="3"/>
  <div v-for="(item,index) in state.guest" :key="index">
      번호 {{index+1}} &nbsp; 
      이름 {{ item.name }} &nbsp; 
      나이 {{ item.age }} &nbsp; 
      제목 {{ item.title }} <hr>
  </div>
</template>

<script>
import {ref, reactive} from 'vue'
export default {
  setup() { 
    const count= ref(2300);
    const info = ref('안내문');

    const increment = () => {
      count.value++; // this.count = this.count+1; this 키워드를 사용하면 에러 발생
      info.value = '   숫자가 증가합니다.';
    };
    
    const decrement = () => {
      count.value--;
      info.value = '   숫자가 감소합니다';
    };
 
    const state = reactive({
      guest : [
            { name:'kim', age:23, title:'apple'},
            { name:'lee', age:31, title:'banana'},
            { name:'goo', age:27, title:'cherry'}
        ]
    });
    
    return{
     count, info, increment, decrement, state
    };
  }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
