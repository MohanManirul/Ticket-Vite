<template>
    <div class="container">
        <h2>Contact List</h2>
        <hr>
         <table class="table table-hover">
        <thead>
            <tr>
                <th scope="col">Sl.</th>
                <th scope="col">Name</th>
                <th scope="col">Email</th>
                <th scope="col">Designation</th>
                <th scope="col">Contact No</th>
                <th scope="col">Action</th>
            </tr>
        </thead>

        <tbody v-for="contact in contacts" :key="contact.id">
            <tr class="table-secondary">
                <th scope="row">{{ contact.id }}</th>
                <th scope="row">{{ contact.name }}</th>
                <th scope="row">{{ contact.email }}</th>
                <th scope="row">{{ contact.designation }}</th>
                <th scope="row">{{ contact.contact_no }}</th>
                <th scope="row"><router-link :to= "{ name:'EditContact', params:{id:contact.id} }" class="btn btn-primary">Edit</router-link></th>
                <th scope="row"><button class="btn btn-danger" @click.prevent="deleteContact(contact.id)">Delete</button></th>
            </tr>
        </tbody>
    </table>
    </div>
   
</template>

<script>
    import axios from 'axios';
    export default {
        name:'ContactList', // normally the name of file
        data(){
            return{
                contacts : Array
            }
        },
        created(){
            this.getContacts();
        },
        methods:{

            // getContacts method Start

           async getContacts(){
            let url = 'http://127.0.0.1:8000/api/contacts' ;
            await axios.get(url).then(response => {
                this.contacts = response.data.contacts ;
                console.log(this.contacts);
           }).catch(error => {
                console.log(error);
           });
           },
           
           // getContacts method Start

            // deleteContact method Start
           async deleteContact(id){
                let url = `http://127.0.0.1:8000/api/delete_contact/${id}`
                await axios.delete(url).then(response => {
                    if(response.data.code == 200){
                        alert(response.data.message);
                    }
                }).catch(error => {
                    console.log(error);
                });
           }
           // deleteContact method end
        },
        mounted(){
            console.log('Contact List Component Mounted');
        }
    }
    // export default {
    //     name:'ContactList',
    //     data(){
    //         return{
    //             contacts : Array
    //         }
    //     },
    //     created(){
    //         this.getContacts();
    //     },
    //     methods: {
    //         async getContacts() {
    //             let url = 'http://127.0.1:8000/api/contacts';
    //             await axios.get(url).then(response =>{
    //                 this.contacts = response.data;
    //                 console.log(this.contacts);
    //             }).catch(error => {
    //                 console.log(error);
    //         });
    //         }
    //     },
    //     mounted(){
    //         console.log('Contact List Mounted...');
    //     }
    // }
</script>