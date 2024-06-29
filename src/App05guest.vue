<template>
  <div>
    <h2> App.vue문서</h2>
    <img src="./assets/images/main_4.jpg" height="150" width="300">
    <p></p>
      디저트 : {{ kind }}<br>
      안내문 : {{ info }}<br>
      카운트 : {{ count }}<p></p>
    <hr color="blue" size="3"/>

    <!-- guest 배열객체 출력 힌트 v-for ul,ol,span,div,p-->
    <div v-for="(item,index) in guest" :key="index">
      번호 {{index+1}} &nbsp; 
      이름 {{ item.name }} &nbsp; 
      나이 {{ item.age }} &nbsp; 
      제목 {{ item.title }} <hr>
    </div>
 </div>
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
    info : '안내문',
    guest : [
        { name:'kim', age:23, title:'apple'},
        { name:'lee', age:31, title:'banana'},
        { name:'goo', age:27, title:'cherry'},
    ] 
  }
 },
 methods:{

 }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
