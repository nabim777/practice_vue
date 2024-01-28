<template>
    <div>
        <img src="../assets/restrologo.png" class="logo" />
        <h3>Sign Up</h3>
        <div class="register">
            <input type="text" v-model="name" placeholder="Enter Name">
            <input type="text" v-model="email" placeholder="Enter Email">
            <input type="password" v-model="password" placeholder="Password">
            <button v-on:click="signUp">Sign up</button>
        </div>
    </div>
</template>

<script>

import axios from "axios"
export default{
    name : 'SignUp',
    data()
    {
        return {
            name: '',
            email: '',
            password: ''
        }
    },
    methods:{
        async signUp()
        {
            console.warn("signUp",this.name,this.email,this.password)
            let result= await axios.post("http://localhost:3000/user",
            {
                name: this.name,
                email: this.email,
                password: this.password
            }
            )
            console.warn(result);
            if(result.status == 201)
            {
                alert("Signup done")
            }
            // JSON.stringify just convert json into string
            localStorage.setItem("user-info",JSON.stringify(result.data))
        }
    }
}
</script>

<style>
.logo{
    height: 220px
  }
  
.register input{
    width: 300px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-left: auto;
    margin-right: auto;
    border: 1px solid skyblue;
}

.register button{
    width: 320px;
    height: 40px;
    border: 1px solid skyblue;
    color: #fff;
    background-color: skyblue;
    transition: border-color 0.3s, background-color 0.3s, color 0.3s;
}
.register button:hover{
    border: 1px solid rgb(15, 157, 201);
    background-color: rgb(15, 157, 201);
    cursor: pointer;
}

</style> 