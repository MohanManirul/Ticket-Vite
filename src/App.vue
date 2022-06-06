<template>
  <header>
    <h3>{{ msg }} hello</h3> <hr>

  </header>
  <label>Gender</label>
  <label><input type="radio"  value="M" v-model="formData.gender">Male</label>
  <label><input type="radio" checked="checked" value="F" v-model="formData.gender">Female</label>
  <label><input type="radio" value="O" v-model="formData.gender">Other</label>
 
 <hr>
<div>
  <h3>Gender : {{ formData.gender }} </h3>
</div>
</template>

<script>

export default {
  data() {
    return {
      msg : "Vue 3 bangla Tutorial",
      formData:{
        firstName:"",
        aboutYou : "",
        gender : ""
      }
    };
  },
};
</script>

