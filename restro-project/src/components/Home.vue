<template>
    <h1>Hello, Welcome on home Page</h1>
</template>

<script>
import router from '@/routes';

export default{
    name: "Home",
    //mounted run whenever the page is reloaded
    mounted(){
        let user = localStorage.getItem("user-info")
        if (!user){
            this.$router.push({name:'SignUp'})
        }
    }
}
</script>