<template>
  <header>
    <h3>{{ msg }} hello</h3> <hr>

  </header>
  <label>Gender</label>

  <select  v-model="formData.language">
    <option value="">Select One</option>
    <option value="B">Bangla</option>
    <option value="E">English</option>
  </select>
 
 <hr>
 <select multiple v-model="formData.skills">
   <option>HTML</option>
   <option>CSS</option>
   <option>JavaScript</option>
   <option>PHP</option>
   <option>MySql</option>
 </select>
<div>
  <h3>Skills : {{ formData.skills }} </h3>
  <h3>Gender : {{ formData.language }} </h3>
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
        gender : "",
        language:"",
        skills:[]
      }
    };
  },
};
</script>

