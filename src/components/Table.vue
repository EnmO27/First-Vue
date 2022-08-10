<template>
    <div>

    <button @click="mainFun">Calcular</button>

    <br>
    <br>

    <label><b>Resultado:</b></label>
    <br>
    <input type="numer" v-model="resultado" style="bold">
    <br>
    <br>
    <br>
    <br>

        <table id="OpTable" align="center">
            <tr>
                <th>Operacion</th>
                <th>Numero 1</th>
                <th>Numero 2</th>
                <th>Resultado</th>

            </tr>
        </table>
    </div>
</template>

<script>

export default {
    name: "OperationsTable",
    data: function(){
        return{
            resultado:0,
        }
    },

    props: {
        Operation: String,
        NumberOne: Number,
        NumberTwo: Number,
        Result: Number
    },

    methods: {
        
    mainFun(){

      let empty=false;
      if(this.NumberOne==''||this.NumberTwo==''){
        empty=true;
        alert('La operacion no puede realizarse si existen campos vacios');
      }

      else if(this.Operation=="Suma"){
        this.sumatoria();
        console.log(this.Result)
      }

      else if(this.Operation=="Resta"){
        this.restatoria();
        console.log(this.Result)
      }

      else if(this.Operation=="Multiplicacion"){
        this.multiplicatoria();
        console.log(this.Result)
      }

      else{
        this.divisoria();
        console.log(this.Result)
      }

      if(empty==false){
      this.nuevaEntrada()
      }
    },

        nuevaEntrada(){
            let OpTable=document.getElementById("OpTable");
            let newRow=OpTable.insertRow();
            let columnOne=newRow.insertCell(0);
            let columnTwo=newRow.insertCell(1);
            let columnThree=newRow.insertCell(2);
            let columnFour=newRow.insertCell(3);

            columnOne.innerHTML=this.Operation;
            columnTwo.innerHTML=this.NumberOne;
            columnThree.innerHTML=this.NumberTwo;
            columnFour.innerHTML=this.resultado;


            console.log("Nueva entrada")
        },

    sumatoria(){
      this.resultado=parseInt(this.NumberOne)+parseInt(this.NumberTwo);
    },

    restatoria(){
      this.resultado=parseInt(this.NumberOne)-parseInt(this.NumberTwo);
    },

    multiplicatoria(){
      this.resultado=parseInt(this.NumberOne)*parseInt(this.NumberTwo);
    },

    divisoria(){
      this.resultado=parseInt(this.NumberOne)/parseInt(this.NumberTwo);
    }
    }
}

</script>

<style scoped>

  th{
    background-color: #42b983;
    color: #2c3e50;
  }

  table{
    text-align: center;
    color:white;
    background-color:#2c3e50;

  }

  button{
    background-color: #2c3e50;
    width: 100px;
    height: 50px;
    font-size: 20px;
    color: white;
  }

  input{
    text-align: center;
    background-color:#2c3e50;
    color: white;
    border-radius: 20px;
    font-size: 20px;
    width: 150px;
  }

</style>
