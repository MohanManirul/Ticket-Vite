<template>
    <div class="contact-details">
        <div>
            <h2 class="contact_heading">Contact Details</h2>
            <p><strong>Name : </strong>{{ name }}</p>
            <p><strong>Website : </strong>{{ website }}</p>
            <p><strong>Address : </strong>{{ address }}</p>
        </div>
    </div>
        
</template>

<script>
  export default {
      inject : ["name" , "website" , "address"],
      props : {},
   data(){
     return {
       msg:"Welcome to vue js"
     }
   }
 }
</script>

<style scoped>
    .contact-details{

        border: 1px solid gray;
        padding: 2px;
        margin: 22px;
    }
    .contact_heading{
        color: blue;
    }
</style>