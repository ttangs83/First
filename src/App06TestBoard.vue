<template>
  <div>
    <h2> App.vue문서</h2>
    <img src="./assets/images/main_4.jpg" height="150" width="300">
    <p></p>
      디저트 : {{ kind }}<br>
      카운트 : {{ count }}<p></p>
    <hr color="blue" size="3"/>

 <BoardTest/>    
 </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'
import BoardTest from './components/BoardTest.vue'

export default {
  name: 'App',
 // components: { Hello }
 components:{BoardTest},
 data(){
  return {
    kind : '라떼녹차cake' ,
    count : 500
  }
 }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
