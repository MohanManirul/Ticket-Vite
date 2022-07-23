<template>
     <header>
    <h3 class="text-center">Vue 3 crud</h3> 
    <hr>
    <div class="container">
        <p>{{ title }}</p>
        <ul>
            <li><router-link to="/">Home</router-link></li>
            <li><router-link to="add_contact">Add Contact</router-link></li>
        </ul>
    </div>

</header>
</template>

<script>
   export default {
    name: 'Header',
    props:{
      title: String
    }
   }
</script>