<template>
    <Header></Header>
    <h1>Hello, Welcome on add resturant pages</h1>
</template>

<script>
import Header from './Header.vue'

export default{
    name: "Add",
    components: {
        Header
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