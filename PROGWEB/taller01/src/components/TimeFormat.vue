<template>
  <div>
    <h1> {{title}} </h1>
    <p> {{textoRandom}} </p>
    <input @keypress.enter="changeFormat()" type="Number" id="input" placeholder="Hora en segundos" v-model="second" min="0"> 
    <br/>
    <p> La cantidad de segundos ingresada equivale a {{this.hrs}} horas, {{this.min}} minutos y {{this.sec}} segundos</p>
  </div>
</template>

<script>
export default {
    name: 'TimeFormat',
    data(){
      return{
        title: "Time format changer",
        textoRandom: "Ingresa una cantidad de segundos y presiona enter:",
        second:"",
        hrs: 0,
        mod: 0,
        min: 0,
        sec: 0
      }
    },
    methods: {
        changeFormat(){
            this.hrs = Math.floor(this.second/3600)
            this.mod = this.second%3600
            this.min = Math.floor(this.mod/60)
            this.sec =  this.mod%60
            // document.write(this.second, " segundos equivalen a ", this.hrs," horas, ", this.min, " minutos y ", this.sec, " segundos")
        }
    },
    computed: {

    }
}
</script>

<style scoped> 

div{
    background-color: #dbd8ff;
    color: #877df9;
    text-align: center;
    font-size: 16px;
    font-family: helvetica
    }
#input {
  width: 50%;
  background-color: #edebff;
  color: #877df9;
  padding: 18px 20px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
::placeholder{
  color: #afabdc;
  font-style: italic;
}
</style>