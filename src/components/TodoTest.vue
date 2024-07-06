<template lang="">
    <div>
        <!--:skytodo = "item" @click-delete="deleteTodo" @toggle-checkbox="greenCheckbox"-->
        <input type="checkbox" :checked="skytodo.checked" @change="myToggleCheckbox"> {{skytodo.checked}}
        <span :style="skytodo.checked ? 'text-decoration:line-through' : '' ">
            {{skytodo.id}} - {{skytodo.text}}
        </span>
        <button @click="myDeleteTodo"> 삭제 </button>

    </div>
</template>
<script>
    export default {
        name: 'TodoTest',
        props:{
            skytodo:{ type:Object, required:true} ,
        },
        methods:{
           // <!--:skytodo = "item" @click-delete="deleteTodo" @toggle-checkbox="greenCheckbox"-->
            myDeleteTodo(){
                console.log('TodoTest.vue myDeleteTodo함수');
                //alert('TodoTest.vue deleteTodo함수');
                //이해해야 하는 함수 this.$emit(인자1,인자2)
                this.$emit('click-delete', this.skytodo.id);
                
            },
            myToggleCheckbox(event){
                console.log('TodoTest.vue myToggleCheckbox함수');
                //alert('TodoTest.vue toggleCheckbox함수');
                //이해해야 하는 함수 this.$emit(인자1,인자2)
                this.$emit('toggle-checkbox',{
                    id:this.skytodo.id ,
                    checked:event.target.checked
                });
            }
        },
    }
</script>
<style lang="">
    
</style>