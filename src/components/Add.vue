<template>
    <Header />
    <h2>Hello User, Welcome on Add Restaurant Page</h2>
    <form class="add">
        <input type="text" name="name" placeholder="Enter Name" v-model="restaurant.name"/>
        <input type="text" name="address" placeholder="Enter Address" v-model="restaurant.address"/>
        <input type="text" name="contact" placeholder="Enter Contact" v-model="restaurant.contact"/>
        <button v-on:click="addRestaurant" type="button">Add New Restaurant</button>
    </form>
</template>

<script>
import Header from './Header.vue'

export default{
    name:"Home",
    components:{
        Header
    },
    data(){
        return{
            restaurant:{
                name:'',
                address:'',
                contact:''

            }
        }
    },
    methods:{
        addRestaurant(){
            console.log(this.restaurant)

        }
    },
    mounted(){
        let user = localStorage.getItem('user-info')
        if(!user){
            this.$router.push({name:'SignUp'})

        }
    }

}
</script>
