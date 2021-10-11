<template>
  <router-view />
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


</style>


<style>

*{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
.logo{
    width:200px;
    height:200px;
    object-fit: cover;

    /*display: block; */
    /* object-fit: contain;
    */
    /* max-width: 200px;
    max-height: 200px;
    width: auto;
    height: auto;  */

}
body{
  margin: 0;
  padding: 0;

}

.register input, .login input, .add input {
    width: 300px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-left: auto;
    margin-right: auto;
    border: 1px solid skyblue;
}


.register button, .login button, .add button {
    background: skyblue;
    width: 320px;
    height: 40ox;
    font-size: 20px;
    font-weight: bold;
    border-radius: 5px;
    padding: 10px;
    border: 1px solid skyblue;
    cursor: pointer;
    color: #fff;
}


</style>