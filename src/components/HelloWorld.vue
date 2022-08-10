<template>
  <div class="templa">
    <h1>V-Calculator</h1>
    <input id="inputOne" type="number" v-model="numero1">
    <br>
    <br>

    <select v-model="operacion">

      <option value="Suma">Suma</option>
      <option value="Resta">Resta</option>
      <option value="Multiplicacion">Multiplicacion</option>
      <option value="Division">Division</option>

    </select>

    <br>
    <br>

    <input id="inputOne" type="number" v-model="numero2">
    
    <br>
    <br>

    <!--<button @click="mainFun">Calcular</button>

    <br>
    <br>

    <label>Resultado:</label>
    <br>
    <input type="numer" v-model="resultado">

    <br>
    <br>-->
    <OperationsTable :Operation="operacion" :NumberOne="numero1" :NumberTwo="numero2" :Result="resultado">></OperationsTable>
  </div>
</template>

<script>
import OperationsTable from './Table.vue'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components:{
    OperationsTable
  },
  data: function(){
    return{
      numero1: 0,
      numero2: 0,
      resultado: 0,
      operacion:"Suma"
    }
  },

  methods:{

    mainFun(){
      if(this.operacion=="Suma"){
        this.sumatoria();
        console.log(this.resultado)
      }

      else if(this.operacion=="Resta"){
        this.restatoria();
        console.log(this.resultado)
      }

      else if(this.operacion=="Multiplicacion"){
        this.multiplicatoria();
        console.log(this.resultado)
      }

      else{
        this.divisoria();
        console.log(this.resultado)
      }

    },

    sumatoria(){
      this.resultado=parseInt(this.numero1)+parseInt(this.numero2);
    },

    restatoria(){
      this.resultado=parseInt(this.numero1)-parseInt(this.numero2);
    },

    multiplicatoria(){
      this.resultado=parseInt(this.numero1)*parseInt(this.numero2);
    },

    divisoria(){
      this.resultado=parseInt(this.numero1)/parseInt(this.numero2);
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

template{
  background-color:#2c3e50;
}

select{
  border-radius: 20px;
  background-color: #2c3e50;
  color: white;
  width: 120px;
  height: 30px;
  font-size: 15px;
  text-align: center;
}

tr{
  color:#2c3e50;
}

input{
  border-radius: 20px;
  width: 200px;
  height: 30px;
  background-color: #42b983;
  font-size: 20px;
  text-align: center;
  
}

h1{
  border: #42b983;
  font-size: 50px;
  border-width: 100px;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
