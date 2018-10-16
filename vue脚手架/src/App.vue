<template>
  <div id="app" class="container tab tabs">
    <img src="./assets/logo.png" alt="" class="img-responsive logo" style="margin:7.5rem auto 0;"/>
    <users></users>
    <hello></hello>
  </div>
</template>

<script>
import Users from './components/Users'
import HelloWorld from './components/HelloWorld'


export default {
  name: 'App',
  components:{
    "users":Users,
    "hello":HelloWorld,
    
  }
  
  
}
</script>

<style>
#app{width: 100%; height: 100%; background: url(./assets/ground.jpeg);  background-size: 100% 100%; background-attachment: fixed;position:absolute}
@media only screen and (min-width: 320px){
    html {
        font-size:10px !important;
    }
}
@media only screen and (min-width: 360px){
    html {
        font-size:11.25px !important;
    }
}
@media only screen and (min-width: 400px){
    html {
        font-size:12.5px !important;
    }
}
@media only screen and (min-width: 480px){
    html {
        font-size:15px !important;
    }
}
@media only screen and (min-width: 640px){
    html {
        font-size:20px !important;
    }
}


</style>
