<template>
    <Header />
    <h2>Hello {{name}}, Welcome on Home Page</h2>
    <table>
        <tr class="headers">
            <td>Id</td>
            <td>Name</td>
            <td>Contact</td>
            <td>Address</td>
        </tr>

        <tr v-for="item in restaurants" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.contact }}</td>
            <td>{{ item.address }}</td>
        </tr>
    </table>
</template>

<script>
import Header from './Header.vue'
import axios from 'axios'

export default{
    name:"Home",
    data(){
        return{
            name:'',
            restaurants:[],

        }

    },
    components:{
        Header
    },
    async mounted(){
        let user = localStorage.getItem('user-info')
        this.name = JSON.parse(user).name
        if(!user){
            this.$router.push({name:'SignUp'})

        }
        let result = await axios.get("http://localhost:3000/restaurant");
        console.warn(result)
        this.restaurants = result.data

    }

}
</script>

<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 50%;
  text-align:center;
  margin:auto;
}

table .headers td{
    font-style: bold;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}

</style>
