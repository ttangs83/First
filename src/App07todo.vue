<template>
  <div>
    <h2> App.vue문서</h2>
    <img src="./assets/images/main_4.jpg" height="150" width="300">
    <p></p>
    <input type="text" v-model="todoText" size=15 @keyup.enter="insertTodo">
    <button @click="insertTodo">todo 등록</button>
    
    
    <div v-for="(item) in todoList" :key="item" style="color:orangered">
      {{ item.checked }} {{ item.id }} - {{ item.text }} &nbsp; 

    </div>

    <hr color="blue" size="3"/>

   
 </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'
// import BoardTest from './components/BoardTest.vue'

export default {
  name: 'App',
 // components: { Hello , BoardTest}
//  components:{BoardTest},
 data(){
  return {
    kind : '라떼녹차cake' ,
    todoText : 'abc'  ,
    count : 1 ,
    todoList : [
        { id:1, text:"kim", checked:'false'},
        { id:2, text:"lee", checked:'true'},
    ]
  }
 },
 methods:{
  insertTodo(){
    // alert("insertTodo 메소드");

    var max = this.todoList.reduce(function(a,b){
      console.log(a);
      return a > b ? a: b.id;
    });

    this.todoList.push({
      id:max+1,
      //id:this.todoList.length+1,
      text:this.todoText,
      checked:false
    }); //배열에 넣기
    this.todoText = '';
    
  }
 }
 
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
