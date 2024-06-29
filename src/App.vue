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
    <TodoTest v-for ="(item) in todoList" :key="item.id" />

    <p></p>
    <Hello msg="모란백합 Welcome"/>
   
 </div>
</template>

<script>
import Hello from './components/HelloWorld.vue'
// import BoardTest from './components/BoardTest.vue'
import TodoTest from './components/TodoTest.vue';

export default {
  name: 'App',
 // components: { Hello , BoardTest}
  components:{ Hello, TodoTest},
  
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
    
  },
  //deleteTodo(id){ //웹브라우저 storage연결
    //var max = this.todoList.reduce(function(a,b){
    //  console.log(a);
    //  return a > b ? a: b.id;
    //});
    //배열추가 push(), 대표값하나추출 reduce(), 찾아서 findIndex()
    // todoList배열 데이터추가는 App.vue처리하고, 삭제는 새로만든 컴포넌트 TodoTest.vue처리
    //id = max;
    //var index = this.todoList.findIndex(); // 7월6일 토요일 삭제처리 여기서 부터 시작
    //this.todoList.splice(index,1);
  //},
  greenCheckbox(){
    console.log("greenCheckbox() 함수");
  },
 }
 
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
