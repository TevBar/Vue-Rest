<template>
    <HeaderTop />
    <h1>Hello User, Welcome on Add Restaurant Page</h1>
    <form class= "add" >
        <input type="text" v-model="restaurant.name" placeholder="Enter Restaurant Name..."/>
        <input type="text" v-model="restaurant.contact" placeholder="Enter Restaurant Address..."/>
        <input type="text" v-model="restaurant.address" placeholder="Enter Restaurant Contact..."/>
        <button v-on:click="addRest" class="btn">Add Restaurant</button>
    </form>
</template>
<script>
import HeaderTop from './HeaderTop.vue';
import axios from 'axios';
export default{
    name: 'AddRest',
    components: {
        HeaderTop
    },
    data()
    {
        return { 
            restaurant: {
                name: '',
                address: '',
                contact: ''
            }
        }
    },
    methods: {
       async addRestaurant()
        {
            console.warn(this.restaurant);
            const result = await axios.post("http://localhost:3001/restaurant",{
                name:this.restaurant.name,
                address:this.restaurant.address,
                contact:this.restaurant.contact,
            });
            console.warn("result",result);
        }
    },
    mounted()
        {
            let user = localStorage.getItem('user-info');
            if(!user)
            {
                this.$router.push({name:'SignUp'})
            
            }
        }
    }
</script> 