<template>
  <div>
    <h2> App.vue문서</h2>
    <img src="./assets/images/a3.png" height="150" width="300">
    <p></p>
    <form @submit.prevent="addGuest"> <!--spa한페이지처럼 운영 = Vue,리액트,Angular,svelte-->
      <input type="text" v-model="newTitle" size=15 placeholder="enter Title">
      <button type="submit">서브밋추가</button>
    </form>
    <div v-for="(item,index) in guests" :key="item.id">
      {{index+1}} - {{ item.title }}
      <button @click="deleteGuest(item.id)">삭제</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';


export default {
  name: 'App',
 
  data(){
  return {
    guests : [ ],
    newTitle:''
  }
 },
 methods:{
  addGuest(){
    if(this.newTitle.trim() === ''){alert('입력란 공백입니다.'); return;}
    const newGuest = {title:this.newTitle};

    axios.post("http://localhost:3000/guests", newGuest)
    .then(response=>{this.guests.push(response.data); this.newTitle='';})
    .catch(error=>{console.log('저장에러',error);});
  },
  displayGuest(){//db.json문서 데티어 id,title 항목 읽어오기 axios이용
    axios.get("http://localhost:3000/guests")
    .then(response=>{this.guests = response.data;}) //모든 데이터 배열에 담아오기
    .catch(error=>{console.log('출력에러',error);});
    //.finally(funtion(){});
  },//displayGuest end
  deleteGuest(id){
    //삭제처리
    //alert(id);
    axios.delete(`http://localhost:3000/guests/${id}`)
    .then(()=>{
      var index = this.guests.findIndex(pt=>{return pt.id === id});
       this.guests.splice(index,1);
      })
    .catch(error=>{console.log('삭제에러',error);

    });
  }
 },
 /**created(){ //Vue 라이프사이클에서 mounted(), created() 뷰 생성될 때 자동인식하는 함수
  this.displayGuest();
 }// 화면이 보여지기 전에 실행**/
 
 mounted(){ // 화면이 보여지고 나서 실행
  this.displayGuest(); // 자동으로 모든데이터 출력호출
 }
 
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
