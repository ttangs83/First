<template>
  <img src="./assets/images/a1.png" height="150" width="300">
  <HelloWorld msg="이가연 Welcome to"/>
  <h3>testing testing 쉬는시간</h3>
  <hr color="blue" size="3"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
