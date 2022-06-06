<template>
  <header>
    <h3>{{ msg }} hello</h3>
  </header>

  <div class="container">
    <div class="tab">
      <div class="tab__menu">
        <!-- render tabs start-->
        <div  v-for="tab in tabs"
         :key="tab"
         class="tab__menu-item"
         :class="{'tab__menu-item--active' : activeTab === tab}"
         @click="activeTab = tab"
         >
          {{ tab }}
        </div>
        <!-- render tabs ends-->
      
      </div>
             
        <!-- render tab form start -->
       <div class="tab__content">
         <br>
         <!-- <Login v-if="activeTab === 'Login'"/>
         <Register v-if="activeTab === 'Register'"/> -->
        <keep-alive>
        <component :is="activeTab"></component>
        </keep-alive>            
       </div>
        <!-- render tab form ends --->
    </div>
  </div>
</template>

<script>
import ContactDetails from "./ContactDetails.vue";
export default {
  data() {
    return {
      msg: "Vue3 Vite Project",
      tabs:["Login" , "Register", "ContactDetails"],
      activeTab:"Login",
      name: "Mamunur Rashid",
      website:"https://rimonbd.com",
      address:"Dhaka"
    };
  },
  methods: {},
  provide(){
    return{
      name:this.name,
      website:this.website,
      address : this.website
    }
  },
  components: {
    ContactDetails
  },
};
</script>

<style>
.tab {
}
.tab__menu {
  display: flex;
}

.tab__menu-item {
  padding: 6px 15px;
  background-color: #dbdbdb;
  cursor: pointer;
}
.tab__menu-item--active {
  color: #fff;
  background-color: rgb(27, 104, 192);
}
input {
  padding: 5px 11px;
  margin-bottom: 11px;
}
</style>
