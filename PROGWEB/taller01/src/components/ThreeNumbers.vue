<template>
    <div>
        <h1> Digite un número y presione Enter</h1>
        <h2>(Ingrese 3) </h2>
        <input @keypress.enter="arrPush()" type="number" v-model="num" id="input" placeholder="Ingrese 3, por favor"><br/>
        <div v-if="items.length == 3">Números ingresados: {{items}}</div><br/>
        <button @click="compare()" id="botoncito"> ¿Cuántos de estos son el mismo número?</button>
        <p>Hay {{xd.length}} números repetidos</p>
    
    </div>
</template>

<script>
export default {
    name: "ThreeNumbers",
    data(){
        return{
            num:"",
            items:[],
            repNum: 0,
            xd:[]
        }
    },
    methods: {
        arrPush(){
            // console.log(this.items)
            return this.items.push(this.num);
        },
        compare(){
            if (this.items[0] == this.items[1] || this.items[0] == this.items[2]){
                this.repNum = this.items[0]
            }
            else if(this.items[1] == this.items[2]){
                this.repNum = this.items[1]
            }
            // else if(a != b && b!=c && a!=c){
            //     console.log("ningun numero se repite")
            // }
            this.xd = this.items.filter(x => x == this.repNum)
            console.log("Hay "+ this.xd.length+" números repetidos")
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
    #botoncito{
    background-color: #7dbdf9;
    font-size: 16px;
    border: none;
    color:  #e3fafd;
    padding: 10px 10px;
    border-radius: 6px;
    font-weight: 800;
    cursor: pointer;
    }
::placeholder{
  color: #a4c9d7;
  font-style: italic;
}
</style>