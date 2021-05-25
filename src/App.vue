<template>
  <div id="app">

 <h1 class="titulo"><strong>Conversor De Moedas</strong> </h1><br><br>

    <div class="linha">
    <Conversor class="ex" moeda-a="USD" moeda-b="BRL"/>   
    <Conversor class="ex" moeda-a="BRL" moeda-b="USD"/>
 </div>

  <div class="linha2">
    <Conversor class="ex" moeda-a="CAD" moeda-b="BRL"/>   
    <Conversor class="ex" moeda-a="BRL" moeda-b="CAD"/>  
 </div>
  <div class="linha3">
    <Conversor class="ex" moeda-a="EUR" moeda-b="BRL"/>   
    <Conversor class="ex" moeda-a="BRL" moeda-b="EUR"/>  
 </div>



  </div>
</template>

<script>
import Conversor from './components/Conversor'



export default {
  name: 'App',
  components: {
   Conversor
  }

}
</script>

<style>


*{
  margin: 0;
  

}

.titulo{
  color: white;
  background: rgba(61, 61, 247, 0.753);
  height: 50px;
  box-shadow: 0px 0px 0px 5px black;
}



#app {

 
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: rgb(153, 167, 247);
}


.linha{

  display: flex;
  justify-content: space-around;
  border-radius: 25px 25px 25px;
}




.linha2{
  margin-top: 30px;
  display: flex;
  justify-content: space-around;
  
}
.linha3{
  margin-top: 30px;
  display: flex;
  justify-content: space-around;
  
}

.ex{
  background: rgb(160, 211, 155);
  border-width: solid;
  border-radius: 20px 0px;
}




</style>
