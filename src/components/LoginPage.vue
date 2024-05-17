<template>
    <div>
        <img class =" logo " src ="../assets/download.png" alt="Restaurant img"/>
    <h1>
        Login
    </h1>
    <div class ="login">
        <input type="text" v-model ="email" placeholder="Enter your email..."/>
        <input type="password" v-model="password" placeholder="Enter your password..."/>
        <button v-on:click="Login" class = " btn ">login</button>
        <p>
            Want to register? <router-link to="/sign-up">signup</router-link>
        </p>
    </div>
    </div>
</template>

<script>
import axios from 'axios';
export default{
    name: "LoginPage",
    data()
    {
        return{
            email: '',
            password: ''
        }
    },
    methods:{
        async Login()
        {
            let result = await axios.get(
                `http://localhost:3001/users?email=${this.email}&password=${this.password}`
                ,
                {
                email: this.email,
                password: this.password
            });
            console.warn(result);
            if(result.status == 200 && result.data.length > 0)
            {
                localStorage.setItem("user-info",JSON.stringify(result.data[0]));
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