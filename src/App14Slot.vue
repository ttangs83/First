<template>
  <img src="./assets/images/a1.png" height="150" width="300">
  <h3>App.vue 11:05</h3>
  <hr color="blue">

  <ChildComponent>
    <template #mypage="{age,city}">
      나이 : {{ age }}<br>
      도시 : {{ city }}
    </template>
  </ChildComponent>
</template>

<script>
import ChildComponent from './components/ChildComponent.vue'

export default {
  name: 'App',
  components: {
    ChildComponent
  }
}
</script>

<style>
#app {
  margin-top: 20px;
}
</style>
