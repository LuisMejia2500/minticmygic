<template>
  <div class="Header">
       <h1>MyGIC</h1>
    <nav>
        <button> <router-link to="/">Inicio</router-link></button>
        <button>Crear</button>
        <button  > Consultar </button>
    </nav>
  </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Header',
  props: {
    msg: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 body{
        margin: 0 0 0 0;
        font-family: /*'Josefin Sans', sans-serif,*/ 'Bungee', cursive;
    }
   .header{
        margin: 0%;
        margin-top: -5%;
        padding: 0;
        width: 100%;
        height: 10px;
        min-height: 100px;
        left:0%;

        background-color: #99FF99 ;
        color:#0f1011  ;

        display: flex;
        justify-content: space-between;
        align-items: center;
   }

   nav{
       margin-right: 60px;
   }
   h1{
       margin-left: 60px;
       font-size: 40pt; 
       font-family: 'Bungee';       
   }
   button{
       font-size: 18pt;
       color: black;
       background-color: white;
       border-radius: 28px;
       padding: 5px 20px;
       margin: 20px;      
   }
   .button:hover{
       background-color: white;
   } 
</style>
