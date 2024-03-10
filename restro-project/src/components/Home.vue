<template>
    <h1>Hello, Welcome on home Page</h1>
</template>

<script>

export default{
    name: "HomePage",
    //mounted run whenever the page is reloaded
    mounted(){
        let user = localStorage.getItem("user-info")
        if (!user){
            this.$router.push({name:'SignUp'})
        }
    }
}
</script>