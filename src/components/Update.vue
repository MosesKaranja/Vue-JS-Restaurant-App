<template>
    <Header />
    <h2>Hello User, Welcome on Update Restaurant Page</h2>
</template>

<script>
import Header from './Header.vue'

export default{
    name:"Home",
    components:{
        Header
    },
    mounted(){
        let user = localStorage.getItem('user-info')
        if(!user){
            this.$router.push({name:'SignUp'})

        }
    }

}
</script>
