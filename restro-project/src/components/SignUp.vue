<template>
    <div>
        <img src="../assets/restrologo.png" class="logo" />
        <h3>Sign Up</h3>
        <div class="register">
            <input type="text" placeholder="Enter Name">
            <input type="text" placeholder="Enter Email">
            <input type="text" placeholder="Enter Name">
            <input type="password" placeholder="Create Password">
            <input type="password" placeholder="Re-type Password">
            <button>Sign up</button>
        </div>
    </div>
</template>

<script>

export default{
    name : 'SignUp'
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