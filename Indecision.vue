<template>
    <img src="https://definicion.de/wp-content/uploads/2020/05/indecision.jpg" />
    <div>
        <h1> {{title}}</h1>
        <input type="text" v-model="question" id="a"><br/>
        {{question}}
    </div>
</template>

<script>
export default {
    name: "INDECISON",
    data(){
        return{
            title:"INDESICION",
            question:"",
            oldValue: this.oldValue,
        }
    },
    watch:{
        question (value, oldValue){
            console.log(value, oldValue);
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
  width: 100%;
  background-color: #edebff;
  color: #877df9;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
</style>