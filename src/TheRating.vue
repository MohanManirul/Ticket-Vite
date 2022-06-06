<template>
    <div class="rating">
        <div class="rating-star" v-for="index in 5" :key="index">
            <img src="/img/rating-rated.png" alt="" style="width:50px;" v-if="index <=  modelValue">
            <img src="/img/rating-unrated.png" alt="" style="width:50px;" v-if="index >  modelValue">
        </div>
    </div>
</template>

<script>
   export default {
       props:{
           modelValue:{
               type: Number,
               default: 0 
           }
       },
       emits:["update:modelValue"]
   }
</script>

<style>
    .rating{
        width: 200px;
        display: flex;
        align-items: center;
    }
    .rating-star{
       cursor: pointer;
       margin: 2px; 
    }
    .rating-star img:hover{
        transform: scale(1.1);
    }
</style>