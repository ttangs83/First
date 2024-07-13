<template>
  <div>
    ChildComponent.vue one<br>
    ChildComponent.vue two<br>
    <slot name="mypage" :age="age" :city="city"></slot>
       
  </div>
</template>

<script>
export default {
  name: 'ChildComponent',
  // 변수 age23 name 길동 선언
  data() {
    return{
      age : 23,
      city : '구로로롱'
    }
  }
}

</script>

<style>

</style>
