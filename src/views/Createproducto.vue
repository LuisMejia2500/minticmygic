
<template>
  <div class="create">
    <div class="formulario">
      <h2>Crear producto </h2>
      <form v-on:submit.prevent="GuardarProducto">
        <ul>
          <li><input type="text" v-model="GuardarProducto.codigo" placeholder="Codigo Producto"></li>
          <li><input type="text"  v-model="GuardarProducto.nombre" placeholder="Nombre Producto"></li>
          <li><input type="text" v-model="GuardarProducto.cantidad_disponible" placeholder="Cantidad disponible"></li>
          <li><input type="text" v-model="GuardarProducto.costo_adquisicion" placeholder="Costo de adquisicion"></li>
          <li><input type="text"  v-model=" GuardarProducto.precio_venta" placeholder="Precio venta"></li>
          <li><input type="text"  v-model=" GuardarProducto.fecha_caducidad" placeholder="Fecha vencimiento"></li>
          <li><button type="submit">CREAR PRODUCTO</button></li>
        </ul>

    </form>

    </div>

     
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import axios from 'axios';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default ({
  name: 'create',
  data:function(){
    return{
      producto:{
        codigo:"",
        nombre:"",
        cantidad_disponible:"",
        costo_adquisicion:"",
        precio_venta:"",
        fecha_caducidad:""
      }
    }
  },
  methods:{
    GuardarProducto:function(){
      let self = this
      axios.post("https://sprint2-grupo3.herokuapp.com/product/", self.GuardarProducto , {headers:{}})
        .then((result)=>{
          alert("El producto fue Registrado Correctamente")
        })
        .catch((error)=>{
          alert("Error" + error.response.status )
        })
    }
  }
  

});

</script>
<style scoped>
div{
  text-align: center;
}
ul{
  list-style: none
}
li{
  margin: 0.5%;
  padding: 2pt;
}
 h2{
   margin-left: 4%;
 }
 input{
   width: 150px;
   border-radius: 20px;
   font-size:15px ;
   height: 20px;
  
 }
 button{
   font-family: Arial;
  color: #ffffff;
  font-size: 15px;
  padding: 10px;
  text-decoration: none;
  -webkit-border-radius: 28px;
  -moz-border-radius: 28px;
  border-radius: 28px;
  -webkit-box-shadow: 0px 1px 3px #666666;
  -moz-box-shadow: 0px 1px 3px #666666;
  box-shadow: 0px 1px 3px #666666;
  text-shadow: 1px 1px 3px #666666;
  border: solid #2a5c28 2px;
  background: #2a5c28;
 
 }
.button:hover {
  background: #000000;
}

h2{
  font-size: 40px;

 
}

.formulario{
    
    border-radius:15px;
    border:solid 2px rgb(0, 0, 0);
    height: 90%;
    width: 90%;
    margin-left: 60px;
    margin-top: 20px;
    background: #ffff80;


}
</style>


