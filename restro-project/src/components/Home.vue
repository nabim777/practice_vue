<template>
    <Header></Header>
    <h1>Hello, {{ name }} Welcome on home Page</h1>
    <table border="1px">
        <tr>
            <th>Id</th>
            <th>Name</th>
            <th>Address</th>
            <th>Contact</th>
            <th>Actions</th>
        </tr>
        <tr v-for="item in resturants" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.address }}</td>
            <td>{{ item.contact }}</td>
            <td><router-link :to="'/update/'+item.id">Update</router-link></td>
        </tr>
    </table>
</template>

<script>

import axios from 'axios';
import Header from './Header.vue'

export default{
    name: "Home",
    components: {
        Header
    },
    data() {
        return {
            name: '',
            resturants: []
        }
    },
    //mounted run whenever the page is reloaded
    async mounted(){
        let user = localStorage.getItem("user-info")
        if (!user){
            this.$router.push({name:'SignUp'})
        }
        else{
            this.name = JSON.parse(user).name
        }
        let result = await axios.get("http://localhost:3000/resturant");
        this.resturants = result.data
    }
}
</script>

<style>
td, th{
    width: 160px;
    height: 40px;
}

</style>