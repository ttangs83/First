<template>
  <h2>App.vue문서</h2>
  <p></p>
  <form @submit.prevent="addGuest">
    제목 : <input type="text" name="title" placeholder="제목입력"><br>
    나이 : <input type="text" name="age" placeholder="나이입력"><br>
    파일 :
    <button type="submit"></button>
  </form>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  // components: {HelloWorld}
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
