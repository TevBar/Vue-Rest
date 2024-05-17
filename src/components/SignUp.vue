<template> 
<img class =" logo " src ="../assets/download.png" alt="Restaurant img"/>
    <h1>
        Sign Up
    </h1>
    <div class ="register">
        <input type="text" v-model ="name" placeholder="Enter your name..."/>
        <input type="text" v-model ="email" placeholder="Enter your email..."/>
        <input type="password" v-model="password" placeholder="Enter your password..."/>
        <button v-on:click="signUp" class = " btn ">Sign Up</button>
        <p>
            Already have an account? <router-link to="/login-page">Login</router-link>
        </p>
    </div>
</template> 
<script>
import axios from "axios";

    export default {
        name: 'signUp',
        data(){
            return {
                name: '',
                email: '',
                password: ''
            }
        },
        methods: { 
            async signUp() {
                let result =  await axios.get('http://localhost:3001/users',{
                    name: this.name,
                    email: this.email,
                    password: this.password
                });

                console.warn(result);
                if(result.status == 200)
                {
                    localStorage.setItem("user-info",JSON.stringify(result.data));
                    this.$router.push({name:'Home'})
                }
            }
        },
        mounted()
        {
            let user = localStorage.getItem('user-info');
            if(user)
            {
                this.$router.push({name:'Home'})
            
            }
        }
    }
</script>

<style>
#app{ 
  text-align: center; 
}
/* .logo{ 
  width: 100px; 
}

.register input {
    width: 300px;
    height: 50px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-right: auto;
    margin-left: auto;
    border: 1px solid skyblue;
}
.register button { 
    width: 320px;
    height: 50px;
    border: 1px solid skyblue;
    background-color: skyblue;
    cursor: pointer;
} */
</style> 