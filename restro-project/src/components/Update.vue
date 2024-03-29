<template>
    <Header></Header>
    <h1>Hello, Welcome on update resturant</h1>
    <form class="add">
        <input type="text" placeholder="Enter Name" v-model="resturant.name" name="name">
        <input type="text" placeholder="Enter Address" v-model="resturant.address" name="Address">
        <input type="text" placeholder="Enter Contact" v-model="resturant.contact" name="Contact">
        <button type="button" v-on:click="updateResturant">Update new Resturant</button>
    </form>
</template>

<script>
import Header from './Header.vue'
import axios from 'axios'

export default{
    name: "Home",
    components: {
        Header
    },
    data(){
        return {
            resturant : {
                name: '',
                address: '',
                contact: ''
            }
        }
    },
    method:{

    },
    //mounted run whenever the page is reloaded
    async mounted(){
        let user = localStorage.getItem("user-info")
        if (!user){
            this.$router.push({name:'SignUp'})
        }
        // since we have assign the id variable in the route.js for component update
        // this.$route.params.id is an variable used for fetching the id from route url
        // http://localhost:3000/resturant/1 will fetch the data having id 1
        let $fullurl = "http://localhost:3000/resturant/" + this.$route.params.id
        let result = await axios.get($fullurl)
        this.resturant = result.data
    }
}
</script>