<template>
  <div>
    <h3> 컴포지션api json-server 접근 test 10:17</h3>
    <img src="./assets/images/main_4.jpg" height="150" width="300">
    <p></p>
    <form @submit.prevent="addGuest"> <!--spa한페이지처럼 운영 = Vue,리액트,Angular,svelte-->
      <input type="text" v-model="newGuest.title" size=15 placeholder="enter Title">
      <button type="submit">서브밋추가</button>
      <p v-if="errorMessage" style="color:red;">{{ errorMessage }}</p>
    </form> <!--입력영역-->

    <div v-for="(item,index) in guests" :key="item.id">
      {{index+1}} - {{ item.title }}
      <button @click="deleteGuest(item.id)">삭제</button>
    </div> <!--출력영역-->
  </div>
</template>

<script setup>
import axios from 'axios';
import {ref,onMounted} from 'vue'

  const guests = ref([ ]);
  const newGuest = ref({title:''});
  const errorMessage = ref('');

  //json-server --watch db.json 실행할 때, command prompt에서 실행
  //컴포지션api는 화살표함수 접근 const 이름 = (data) = > 구현
  //컴포지션api는 최대한 this사용금지
  const displayGuest = () => axios.get("http://localhost:3000/guests")
    .then(response=>{guests.value = response.data;}) //모든 데이터 배열에 담아오기
    .catch(error=>{console.log('composition 출력에러',error);});
  
  const addGuest = () => 
    axios.post("http://localhost:3000/guests", newGuest.value)
    .then(response=>{
      if(newGuest.value.title === ''){
        errorMessage.value = '입력된 데이터가 없습니다.';
        return;
      }else if(newGuest.value.title.length <= 1){
        errorMessage.value = '입력 데이터는 최소 2글자 입니다.';
        newGuest.value={title:''};
        return;
      }else{ 
        errorMessage.value = '';     
        guests.value.push(response.data); 
        newGuest.value={title:''};
    }
    
    }
    )
    .catch(error=>{console.log('composition 저장에러',error);});
  
  const deleteGuest = (id) =>
    axios.delete(`http://localhost:3000/guests/${id}`)
    .then(()=>{
      var index = guests.value.findIndex(pt=>{return pt.id === id});
      guests.value.splice(index,1);
    })
    .catch(error=>{
      console.log('삭제에러',error);
    });
 
  onMounted(displayGuest); //vue라이프사이클 onCreated후 화면보여지는 상태가 onMounted
  //기존 자바스크립트 함수
  // function 함수명() {구현}
  // 함수명 = () => {구현}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
