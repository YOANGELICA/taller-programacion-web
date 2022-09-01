<template>
    <div>
        <h1> {{title}} </h1>
        <p> Digite un salario y presione Enter.</p>
        <input @keypress.enter="arrPush()" type="number" min="0" v-model="newSalary" id="a" placeholder="Por favor ingrese 10 salarios"><br/>
        <p>Salarios ingresados: {{items.length}}</p>
        <button @click="delSalary()" class="botoncito"> Borrar el último salario </button> <br/>
        <p>Presione el botón para ver los salarios con un aumento del 0.8% </p>
        <button @click="customSal()" class="botoncito"> +0.8% </button>
        <ul v-for="(item, index) in newItems">
            <li> Salario {{index+1}}: {{item}} </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Salary",
    data(){
        return{
            title: "Salary calculator",
            newSalary: "",
            items:[],
            newItems: []
        }
    },
    methods: {
        arrPush(){
            // console.log(this.items)
            return this.items.push(this.newSalary);
        },
        customSal(){
            if (this.items.length < 10){
                alert("Por favor ingrese los salarios restantes");
            }
            else if(this.items.length > 10){
                alert("Por favor ingrese exactamente 10 salarios");
            }
            else if (this.items.length == 10){
                this.newItems = this.items.map(x => x + x *0.8);
            }
        },
        delSalary(){
            return this.items.pop()
        }
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

    #a{
  width: 30%;
  background-color: #edebff;
  color: #877df9;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
.botoncito{
    background-color: #8880e8;
    color:  #e8e6ff;
    border-radius: 6px;
    border: none;
    padding: 8px 10px;
    font-weight: 800;
    cursor: pointer;

}
::placeholder{
    color:  #aea6f6;
    font-style: italic;
}
</style>