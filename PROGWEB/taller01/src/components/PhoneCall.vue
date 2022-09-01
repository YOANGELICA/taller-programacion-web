<template>
    <div>
        <h1>Determine el precio de su llamada telefónica</h1> <br/>
        <p>Ingrese la duración de la llamada en minutos:</p> <br/>
        <input @keypress.enter="det_price()" type="number" id="input" placeholder="Duración de la llamada" v-model="len" min="0"> <br/>
        <p>El precio de su llamada de {{len}} minutos es de ${{price}} pesos </p>
    </div>
</template>

<script>
export default{
    name: "PhoneCall",
    data(){
        return{
            len: "",
            price: 0
        }
    },
    methods: {
        det_price(){
            if (this.len < 4){
                return this.price = 100;
            }
            else if (this.len >= 4){
                return this.price = 100 + 50*(this.len-3);
            }
        }
    },
    computed: {}
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
    #input {
  width: 50%;
  background-color: #feeaf9;
  color: #f97ddc;
  padding: 18px 20px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
::placeholder{
  color: rgb(220, 171, 211);
  font-style: italic;
}
</style>