<template>
    <HeaderTop />
    <h1>Hello User , welcome to the Update restaurant Page!</h1>
</template>
<script>
import HeaderTop from './HeaderTop.vue';
export default{
    name: 'UpdateRest',
    components: {
        HeaderTop
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