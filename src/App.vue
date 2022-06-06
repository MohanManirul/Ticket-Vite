<template>
  <header>
    <h3>{{ msg }} hello</h3>
  </header>

  <div class="container">
    <h1>New User Registration</h1>
    <label>Full Name</label><br>
    <input type="text" placeholder="Enter your full name" v-model="formData.firstName">
  </div>
  <hr>
  <label for="">About You</label> <hr/>
  <textarea v-model="formData.aboutYou"></textarea>
  <hr>

  <div v-for="(value , key) in formData" :key="key">
    <strong>{{key}} : </strong> {{ value }}
  </div>
</template>

<script>

export default {
  data() {
    return {
      msg : "Vue 3 bangla Tutorial",
      formData:{
        firstName:"",
        aboutYou : ""
      }
    };
  },
};
</script>

