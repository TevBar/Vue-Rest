<template>
    <HeaderTop />
    <h1>Hello {{name}}, welcome to the Home Page!</h1>
    <table border = "1">
        <tr>
            <th>id</th>
            <th>name</th>
            <th>contact</th>
            <th>address</th>
        </tr>
        <tr v-for="item in restaurant" :key="item.id">
            <td>{{item.id}}</td>
            <td>{{item.name}}</td>
            <td>{{item.contact}}</td>
            <td>{{item.address}}</td>
        </tr>
    </table>
</template>
<script>
import HeaderTop from './HeaderTop.vue';
import axios from 'axios';
export default{
    name: 'HomePage',
    data(){
        return {
            name:'',
            restaurant:[],
        }
    },
    components: {
        HeaderTop,
    },
    async mounted()
        {
            let user = localStorage.getItem('user-info');
            this.name = JSON.parse(user).name;
            if(!user)
            {
                this.$router.push({name:'SignUp'})
            }
            let result = await axios.get("http://localhost:3001/restaurant");
            console.warn(result);
            this.restaurant = result.data;
        }
    }
</script> 

<style>
td{
    width: 160px;
    height: 40px;
}
</style>