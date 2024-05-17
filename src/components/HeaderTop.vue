<template>
    <div class="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/add-rest">Add Restuarant</router-link>
        <router-link to="/update-rest">Update Restaurant</router-link>
        <a v-on:click="logout" href="#">Logout</a>
    </div>
</template>

<script>
    export default{
        name: "HeaderTop",
        methods:{ 
            logout()
            {
                localStorage.clear();
                this.$router.push({name:'LoginPage'})
            }
        }
    }
</script>
<style>
.nav{
    background-color: black;
    overflow: hidden;
    display: flex;
    align-items: center;
}

.nav a { 
    float: left;
    color: white;
    padding: 14px 16px;
    text-decoration: none;
    text-align: center;
    margin-right: 20px;
    font-size: 17px;
    cursor: pointer;
}

.nav a:hover{
    background: #ddd;
    color: black;
}
</style>