<template>
    <div>
        <h1> {{title}}</h1>
        <input @keypress.enter="odd()" type="number" v-model="num" id="a" placeholder="Inserta un número"><br/>
        <p> Los números impares menores que el número {{num}} son: {{this.nums}}</p>
        <!-- <p> Los números impares menores que {{num}} son: </p> <br/>
        <li v-for="(x) in nums"> {{x}} </li> -->

    </div>
</template>

<script>
export default {
    name: "OddNumber",
    data(){
        return{
            title:"ODD NUMBERS",
            nums: [],
            x:0,
            num:""
        }
    },
    methods: {
        odd(){
            while(this.x < this.num){
                if(this.x%2 != 0){
                this.nums.push(this.x)
                }
            this.x +=1
            }
        }
    }
}
</script>

<style scoped>
    div{
    background-color: #fcebb5;
    color: #ffb27a;
    text-align: center;
    font-size: 16px;
    font-family: Raleway,sans-serif
    }

    #a{
  width: 32%;
  background-color: #fffae9;
  color: #ffb27a;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
::placeholder {
  color: #ebcea5;
  font-size: 1em;
  font-style: italic;

}
</style>