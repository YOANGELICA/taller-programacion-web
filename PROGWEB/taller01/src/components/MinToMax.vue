<template>
    <div>
        <h1> {{title}} </h1>
        <p> Ingrese un numero y presione enter. </p>
        <input @keypress.enter="arrPush()" type="number" v-model="num" id="input" placeholder="Ingrese la cantidad que desee..."><br/>
        <ul>
        <li v-for="(item) in items">
            <span> {{item}} </span>
        </li>
        </ul>
        <p> (Presione el botón para ordenar los números)</p>
        <button @click="orderList()" id="botoncito"> Ordenar </button> <br/>
    </div>

</template>
<script>
export default {
    name: "MinToMax",
    data(){
        return{
            title: "List Ordering",
            num: "",
            items:[
            ]
        }
    },
    methods: {
        orderList(){
            return this.items.sort((a,b)=>a-b);
        }
    },
    computed: {
        arrPush(){
            return this.items.push(this.num);
        },
    }
}
</script>

<style scoped>
    div{
    background-color: #ffd8f6;
    color: #f97ddc;
    text-align: center;
    font-size: 16px;
    font-family: helvetica
    }

    #input{
  width: 50%;
  background-color: #feeaf9;
  color: #f97ddc;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
#botoncito{
    background-color: #f97ddc;
    color:  #feeaf9;
    border-radius: 6px;
    border: none;
    padding: 8px 10px;
    font-weight: 800
}
::placeholder{
  color: #dfb8d6;
  font-style: italic;
}
</style>