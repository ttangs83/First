<template>
  <h2> App.vue문서</h2>
  <img src="./assets/images/a3.png" height="150" width="300">
  <p></p>
    <!--디저트 : {{ kind }}<br> -->
    안내문 : {{ info }}<br>
    <h3>카운트 : {{ count }}</h3><p></p>
    <button @click="suIncrement">증가1</button> &nbsp;
    <button @click="suDecrement">감소1</button> &nbsp;
    <button v-on:click="suIncrement">증가2</button> &nbsp;
    <button v-on:click="suDecrement">감소2</button>

  <hr color="blue" size="3"/>
  <div v-for="(item,index) in guest" :key="index">
      번호 {{index+1}} &nbsp; 
      이름 {{ item.name }} &nbsp; 
      나이 {{ item.age }} &nbsp; 
      제목 {{ item.title }} <hr>
    </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'

export default {
  name: 'App',
 // components: { Hello }
 data(){
  return {
    // kind : '라떼녹차cake' ,
    count : 2300,
    info : '안내문' ,
    guest : [
        { name:'kim', age:23, title:'apple'},
        { name:'lee', age:31, title:'banana'},
        { name:'goo', age:27, title:'cherry'},
    ] 
  }
 },
 methods:{
  suIncrement(){
    this.count = this.count+1;
    this.info = this.count + '   숫자가 증가합니다.';
    //this.info = this.count;
  },
  suDecrement(){
    this.count = this.count-1;
    this.info = this.count + '   숫자가 감소합니다';
    //this.info = this.count;
  }
 }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
