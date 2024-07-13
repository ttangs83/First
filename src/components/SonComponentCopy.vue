<template>
  <div>
    <hr color="blue">
    <h3>SonComponent.vue 문서 점심식사 후</h3>
    
    <div>
        이름 <input type="text" size="5" @blur="testCap"
                   :value="name" @input="$emit('update:name',$event.target.value)"/> <br>
        <!--input의 내용을 변경시, @blur를 이용하여 커서가 out되면 testCap 메소드 실행하여 앞글자 대문자 변환. focusout도 되는디...-->
        hp : <input type="text" size="5" 
                   :value="hp" @input="$emit('update:hp', $event.target.value)"/>
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
  emits:{
    event : '{update:name, update:hp} '
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
  created(){
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

if(gender === 1 || gender === 3 ){
    남
}else if(gender === 2 || gender === 4){
    여
}
