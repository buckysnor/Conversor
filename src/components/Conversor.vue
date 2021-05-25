<template>
<div class="conversor">

<h2>{{moedaA}} Para {{moedaB}}</h2><br>
<input class="texto" type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
<input class="botao" type="button" value="converter" v-on:click="converter"><br><br><br>
<h2 class="B">{{moedaB_value}} </h2>


</div>

</template>




<script>  


export default{

    name:"Conversor",
    props:["moedaA","moedaB"],

    data(){
        return { 
            moedaA_value:"",
            moedaB_value: 0
        };

    },

      methods:{

      converter() {

          let de_para = this.moedaA + "_" + this.moedaB;

         let url = 
         "https://free.currconv.com/api/v7/convert?q=" +
          de_para +
         "&compact=ultra&apiKey=78848aa5069cec6d3037";
          
          fetch(url)
            .then(res => {
                return res.json();
                
          })
          
          
            .then(json => {
               
              let cotacao = json[de_para];
              this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(
                  2
                  );
              
        });
    }

}
}
</script>




<style scoped>


.conversor{
height: 147px;
width: 300px;
box-shadow: 0px 5px 10px 1px black;
padding: 20px;


}

.B{
    background-color:  rgba(119, 119, 240, 0.616);
    border-radius: 10px;
    width: 50px;
    text-align: center;
    box-shadow: 0px 3px 2px;
}


.botao{
    
    border-radius: 5px 5px 5px 5px;
    box-shadow: 1px 1px 0px px;
}


.texto{
    border-radius: 5px 5px 5px;
    box-shadow: 0px 1px;
}


</style>