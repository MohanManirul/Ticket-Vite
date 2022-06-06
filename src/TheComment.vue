<template>
    <h3>Write your comment bellow</h3>

    <div class="the-comment">
        <textarea :value="modelValue" @input="handleInput" v-bind="$attrs">
        <div class="text-align">
            <button @click="$emit('continueClick')">{{ buttonText }}</button>
        </div>
    </div>

</template>

<script>
   export default {
       props:{
           modelValue:{
               type:String,
               default: ""
           },
           buttonText : {
               type : String,
               default:"ok"
           }
       },
       inheritAttrs : false,
       created(){

       },
       methods:{
           handleInput(e){
               this.$emit("update:modelValue" , e.target.value);
           }
       }
   }
</script>