<template>
    <Header></Header>
    <h1>Hello, Welcome on update resturant</h1>
</template>

<script>
import Header from './Header.vue'

export default{
    name: "Home",
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