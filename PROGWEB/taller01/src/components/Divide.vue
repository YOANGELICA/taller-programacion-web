<template>
    <div> 
        <input type="text" v-model="index" id="input" placeholder="Posición del Arreglo" @keyup="create()">
        <br>
        <p v-if="index<10">
            <h3>Arreglo: {{arr}}</h3> <br/>
            <button @click="divide()" id="botoncito"> Dividir </button><br/>
            <h3>Números divididos: {{div}} </h3>
        </p>
        <p v-else> La posición {{index}} no se encuentra en el arreglo</p>
    </div>
</template>

<script>
  export default {
    name: 'Aleatorio',
    data(){
        return{
            arr: undefined,
            index: '',
            div:[]

        }
    },
    methods: {
        create(){
            this.arr = new Array(10);
            for (let i = 0; i < this.arr.length; i++) {
                this.arr[i] = Math.floor(Math.random()*100);
            }
        },
        divide(){
            for (let i = 0; i < this.arr.length; i++) {
                // this.div[i] = (this.arr[i]/this.arr[this.index].toFixed(2))
                this.div[i] = parseFloat((this.arr[i]/this.arr[this.index]).toFixed(2));
                if(this.arr[i] == 0){
                alert("Error: el divisor es 0");
            }
            }
          }
        }
    }
  
</script>

<style scoped>
    div{
    background-color: #caeaf7;
    color: #7dbdf9;
    text-align: center;
    font-size: 16px;
    font-family: helvetica
    }
    #botoncito{
    background-color: #7dbdf9;
    font-size: 16px;
    border: none;
    color:  #e3fafd;
    padding: 10px 10px;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 800
    }
    #input{
  width: 32%;
  background-color: #ebfcff;
  color: #7dbdf9;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
::placeholder{
  color: #a4c9d7;
  font-style: italic;
}
</style>