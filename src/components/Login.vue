<template>
 <div>
        <img src="../assets/restrologo.png" class="logo" alt="resturant" />
        <h3>Login</h3>
        <div class="login">
            <input type="text" v-model="email" placeholder="Enter Name or email">
            <input type="password" v-model="password" placeholder="Password">
            <button v-on:click="login">Login</button>
            <p>
                <router-link to="/Sign-Up">Sign Up</router-link>
            </p>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default{
    name : 'login',
    data(){
        return {
            email: '',
            password: ''
        } 
    },
    methods:{
        async login()
        {
            // http://localhost:3000/user?email=nabinaale@gmail.com&password=@123
            // this is api for filtering the required username with email and password
            let result= await axios.get(`http://localhost:3000/user?email=${this.email}&password=${this.password}`)
            console.warn(result)
            if(result.status==200 && result.data.length>0){
                // JSON.stringify just convert json into string
                localStorage.setItem("user-info",JSON.stringify(result.data[0]))
                //this will navigate to home.vue
                this.$router.push({name:'Home'})
            }
        }  
    },
        //mounted will load whenever page is loaded
        //this will check the value in application storage if there is user it will redirect to the home page
    mounted(){
        //this will get the value from loaclstorage named user-info
        let user = localStorage.getItem('user-info');
        //if user is login then redirect homepage
        if (user){
            this.$router.push({name:'Home'})
        }
    }
}
</script>