<template>
  <h2> App.vue문서</h2>
  <img src="./assets/images/main_4.jpg" height="150" width="300">
  <Hello msg="이가연 Welcome to"/>
  <h3>testing testing 쉬는시간</h3>
  <hr color="blue" size="3"/>
</template>

<script>
import Hello from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    Hello
  }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
