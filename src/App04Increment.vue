<template>
  <h2> App.vue문서</h2>
  <img src="./assets/images/a3.png" height="150" width="300">
  <p></p>
    디저트 : {{ kind }}<br>
    안내문 : {{ info }}<br>
    <h3>카운트 : {{ count }}</h3><p></p>
    <button @click="suIncrement">증가1</button> &nbsp;
    <button @click="suDecrement">감소1</button> &nbsp;
    <button v-on:click="suIncrement">증가2</button> &nbsp;
    <button v-on:click="suDecrement">감소2</button> <p></p>

    <button @click="suIncrement()">증가3</button> &nbsp; 
    <button @click="suDecrement()">감소3</button> <p></p> 



  <hr color="blue" size="3"/>
</template>

<script>
//import Hello from './components/HelloWorld.vue'

export default {
  name: 'App',
 // components: { Hello }
 data(){
  return {
    kind : '라떼녹차cake' ,
    count : 1000,
    info : '안내문'
  }
 },
 methods:{
  suIncrement(){
    this.count = this.count+1;
    //this.info = this.count;
  },
  suDecrement(){
    this.count = this.count-1;
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
