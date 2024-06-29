<template lang="">
    <div>


    </div>
</template>
<script>
    export default {
        name: 'TodoTest',
        data(){
            return {
                lotto: 1 ,
            }
        },
        methods:{
            deleteTodo(){
                console.log('TodoTest.vue deleteTodo함수');
                alert('TodoTest.vue deleteTodo함수');
                //이해해야 하는 함수 this.$emit(인자1,인자2)
                
            },
            toggleCheckbox(){
                console.log('TodoTest.vue toggleCheckbox함수');
                alert('TodoTest.vue toggleCheckbox함수');
                //이해해야 하는 함수 this.$emit(인자1,인자2)
            }
        },
    }
</script>
<style lang="scss" scoped>
    
</style>