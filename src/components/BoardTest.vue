<template lang="">
    <div>
        <img src="../assets/images/a3.png" height="150" width="300">
        BoardTest.vue
        <!-- guest 배열객체 출력 힌트 v-for ul,ol,span,div,p-->
        <div v-for="(item,index) in guest" :key="item">
        번호 {{(index+1)}} &nbsp; 
        이름 {{ item.name }} &nbsp; 
        나이 {{ item.age }} &nbsp; 
        제목 {{ item.title }} <hr>
        </div>
    </div>
</template>
<script>
export default {
  name: 'BoardTest',
  data(){
  return {
    name : "Hong gil dong",
    guest : [
        { name:'kim', age:23, title:'apple'},
        { name:'lee', age:31, title:'banana'},
        { name:'goo', age:27, title:'cherry'},
    ]
  }
 },
 methods:{

 }
}
    
</script>
<style lang="scss" scoped>
    
</style>