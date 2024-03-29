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
    mounted(){
        let user = localStorage.getItem("user-info")
        if (!user){
            this.$router.push({name:'SignUp'})
        }
    }
}
</script>