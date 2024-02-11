<template>
 <div>
        <img src="../assets/restrologo.png" class="logo" />
        <h3>Login</h3>
        <div class="login">
            <input type="text" v-model="name" placeholder="Enter Name or email">
            <input type="password" v-model="password" placeholder="Password">
            <button>Login</button>
            <p>
                <router-link to="/Sign-Up">Sign Up</router-link>
            </p>
        </div>
    </div>
</template>

<script>
export default{
    name : 'login',
}
</script>

<style>
</style>