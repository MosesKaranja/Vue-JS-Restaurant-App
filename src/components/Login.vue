<template>
    <img class="logo" src="../assets/preview.png"/>
    <h1>Login</h1>
    <div class="login">
        <input type="text" v-model="email"  placeholder="Enter Email"/>
        <input type="password" v-model="password" placeholder="Enter Password"/>
        <button v-on:click="login">Login</button>
        <p>
            <router-link to="/sign-up">Sign Up</router-link>
        </p>
    </div>
    
</template>

<script>
import axios from 'axios'
export default{
    name: 'SignUp',
    data(){
        return{
            email:'',
            password:''
        }
    },
    methods:{
        async login(){
            //console.warn("Login Called, email is: " + this.email + " password is: " + this.password)

            let result = await axios.get(`http://localhost:3000/users?email=${this.email}&password=${this.password}`)
            console.warn(result)
            

            // let result = await axios.get('http://localhost:3000/users?email='+this.email+'&'+'password'+'='+this.password)
    
            // console.warn("De result: "+result)
            // console.warn("De Url: " + 'http://localhost:3000/users?email='+this.email+'&'+'password'+'='+this.password)
        


    
            console.log("De result: "+result)

            if(result.status == 200 && result.data.length > 0){
                //alert("Sign Up")
                localStorage.setItem("user-info", JSON.stringify(result.data))
                this.$router.push({name:"Home"})

            }
            else{
                alert("Wrong email to password combination")
            }

        }
    },
    mounted(){
        let user = localStorage.getItem('user-info')
        console.log("User LocalStorage: ", user)
        if(user){
            this.$router.push({name:'Home'})

        }

    }

}
</script>

<style>

</style>