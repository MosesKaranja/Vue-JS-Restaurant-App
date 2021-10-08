<template>
    <h2>Hello User, Welcome on Home Page</h2>
</template>

<script>
export default{
    name:"Home",

    mounted(){
        let user = localStorage.getItem('user-info')
        if(!user){
            this.$router.push({name:'SignUp'})

        }
    }

}
</script>
