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
        addRestaurant()
        {
            console.warn(this.restaurant);
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