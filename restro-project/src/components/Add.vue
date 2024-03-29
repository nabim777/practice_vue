<template>
    <Header></Header>
    <h1>Hello, Welcome on add resturant pages</h1>
    <form class="add">
        <input type="text" placeholder="Enter Name" v-model="resturant.name" name="name">
        <input type="text" placeholder="Enter Address" v-model="resturant.address" name="Address">
        <input type="text" placeholder="Enter Contact" v-model="resturant.contact" name="Contact">
        <button type="button" v-on:click="addResturant">Add new Resturant</button>
    </form>
</template>

<script>
import Header from './Header.vue'

export default{
    name: "Add",
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
    methods:{
        addResturant(){
            console.log(this.resturant);
        }

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