<template>
    <div>
       <h1>¿Qué hora es?</h1>
       <select type="text" class="a" v-model="hora">
            <option value="0">12 a.m.</option>
            <option value="1">1 a.m.</option>
            <option value="2">2 a.m.</option>
            <option value="3">3 a.m.</option>
            <option value="4">4 a.m.</option>
            <option value="5">5 a.m.</option>
            <option value="6">6 a.m.</option>
            <option value="7">7 a.m.</option>
            <option value="8">8 a.m.</option>
            <option value="9">9 a.m.</option>
            <option value="10">10 a.m.</option>
            <option value="11">11 a.m.</option>
            <option value="12">12 m</option>
            <option value="13">1 p.m.</option>
            <option value="14">2 p.m.</option>
            <option value="15">3 p.m.</option>
            <option value="16">4 p.m.</option>
            <option value="17">5 p.m.</option>
            <option value="18">6 p.m.</option>
            <option value="19">8 p.m.</option>
            <option value="20">9 p.m.</option>
            <option value="21">10 p.m.</option>
            <option value="22">11 p.m.</option>
       </select>
       <!-- {{hora}} -->
       <h2> ¿Cómo te llamas?</h2>
       <input type="text" @keypress.enter="saludar()" v-model="nombre" id="input" class="a" placeholder="Escribe y presiona Enter"><br/>
       <!-- <button @click="saludar()" id="botoncito" class="a"> Continuar </button> <br/> -->
       <p> {{greeting}}, {{nombre}}</p>

    </div>
</template>

<script>
export default{
    name: "Greetings",
    data(){
        return{
            nombre:"",
            hora:"",
            greeting:""
        }
    },
    methods:{
        saludar(){
            if(this.hora < 12){
                return this.greeting = "Buenos días";
            }
            else if(this.hora > 11 && this.hora < 18){
                return this.greeting = "Buenas tardes";
            }
            else if (this.hora > 17){
                return this.greeting = "Buenas noches";
            }
        }
    }
}
</script>

<style scoped>
div{
    background-color: #d5f1b5;
    color: #8ac447;
    text-align: center;
    font-size: 16px;
    font-family: helvetica
    }

.a{
  width: 30%;
  background-color: #e8fbd2;
  color: #69d985;
  padding: 10px 5px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: pointer;
}
#input{
  cursor: text;
}
#botoncito{
    width: 20%;
    background-color: #87d767;
    color:  #e8fbd2;
    border-radius: 6px;
    border: none;
    padding: 8px 10px;
}
::placeholder{
    color:#bad598;
    font-style: italic;
}
</style>