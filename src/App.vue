<template>
  <Header title="Vue Vite Project" />
  <router-view></router-view>
</template>

<script>
import Header from './components/Header.vue'
export default {
  name:'App',
  components: {
    Header
    
  }
};
</script>

<style>
  .text-center{
    text-align: center;
    font-size: 30px;
  }
</style>

