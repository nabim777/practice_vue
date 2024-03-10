<template>
    <div class="nav">
        <a href="#">Home</a>
        <a href="#">Add Resturant</a>
        <a href="#">Update Resturant</a>
        <a href="#">Logout</a>
    </div>
</template>

<script>

export default({
    name: 'Header',
})
</script>

<style>
.nav{
    background-color: #333;
    overflow: hidden;

}

.nav a{
    text-align: center;
    color: #f2f2f2;
    float: left;
    padding: 16px 14px;
    text-decoration: none;
    font-size: 16px; 
    margin-right: 4px;
}

.nav a:hover{
    background-color: #ddd;
    color:#222
}

</style>