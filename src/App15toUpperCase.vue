<template>
  <h2>App.vue 문서 2:15</h2>
  <img src="./assets/images/main_1.jpg" height="150" width="300"> <br>
  App.vue 이름데이터 {{ name }} 입니다.<br>
  App.vue 역량데이터 {{ hp }} 입니다.
  <SonComponent v-model:name="name" v-model:hp="hp"></SonComponent>
  <!--App.vue문서에서는 첫글자 대문자 변환 구현을 하지 않았다.-->
</template>

<script>
import SonComponent from './components/SonComponent.vue';

export default {
  name: 'App',
  components: {SonComponent},
  data(){
    return{
      name: 'tmedic',
      hp:70
    }
  }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
