<template>
    <Header></Header>
    <h1>Hello, {{ name }} Welcome on home Page</h1>
</template>

<script>

import Header from './Header.vue'

export default{
    name: "Home",
    components: {
        Header
    },
    data() {
        return {
            name: ''
        }
    },
    //mounted run whenever the page is reloaded
    mounted(){
        let user = localStorage.getItem("user-info")
        if (!user){
            this.$router.push({name:'SignUp'})
        }
        else{
            this.name = JSON.parse(user).name
        }
    }
}
</script>