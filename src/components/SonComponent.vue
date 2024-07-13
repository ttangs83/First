<template>
  <div>
    <hr color="blue">
    <h3>SonComponent.vue 문서 점심식사 후</h3>
    
    <div>
       <!-- input의 내용을 변경시, @blur를 이용하여 커서가 out되면 testCap 메소드 실행하여 앞글자 대문자 변환. focusout도 되는디...-->
       <!--이름 <input type="text" size="5" @blur="testCap"
                   :value="name" @input="$emit('update:name',$event.target.value)"/> <br>
       
        hp : <input type="text" size="5" 
                   :value="hp" @input="$emit('update:hp', $event.target.value)"/>-->
        <br>
        <!-- :value를 v-model로 변경 -->
        <!--이름2 <input type="text" size="5" @blur="testCap"
                   v-model ="interName" @input="$emit('update:name',$event.target.value)"/> <br>
        hp2 : <input type="text" size="5" 
                   v-model ="interHp" @input="$emit('update:hp', $event.target.value)"/>-->
        <br>
        <!-- @blur="testCap" 입력대신에 @input="testCap"로 변경시, 입력할 때 자동으로 앞글자 대문자로 변경됨-->
        이름3 <input type="text" size="5"
                   v-model ="interName" @input="testCap"/> <br>
        hp3 : <input type="text" size="5" 
                   v-model ="interHp" @input="$emit('update:hp', $event.target.value)"/>
        <!--결론은 App.vue문서는 데이터만 보내면 변경적용된 내용을 다시 App.vue문서로 보냄 
            App.vue문서에서는 <SonComponent v-model:name="name" v-model:hp="hp"></SonComponent> 를 통해 자식데이터를 부르기만할뿐..-->
    </div>
    
    
    
    
    <!--<slot name="mypage" :age="age" :city="city"></slot>-->
       
  </div>
</template>

<script>
export default {
  name: 'SonComponent',
  props:{
    name : {type:String, default:''},
    hp : {type:Number, default:0}
  },
  data() {
    return{
      interName : this.name,
      interHp : this.hp
    }
  },
  methods:{
    
    testCap(){
        //첫글자만 대문자표시 charAt(). toUppercase(), slice(1) 1번째부터 마지막까지
        const mycap = this.interName.charAt(0).toUpperCase() + this.interName.slice(1);
        this.$emit('update:name',mycap); 
    }
  },
  created(){  // 처음실행시 자동적용. 주석처리시, 시작할 때 첫글자 대문자 변경안됨
    const mycap = this.interName.charAt(0).toUpperCase() + this.interName.slice(1);
    
    this.$emit('update:name',mycap); 
    //TodoTest.vue 참고
    //this.$emit('click-delete', this.skytodo.id); 와 비교
  },
   watch:{ // 속성 항목값이 변경되면 지켜보면서 자동갱신변경적용
     name(newVal){
         this.interName = newVal;
     },
     hp(newVal){
         this.interHp = newVal;
     }
   } 
}

</script>

<style>

</style>
