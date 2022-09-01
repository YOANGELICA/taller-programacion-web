<template>
  <div>
    <img :src = 'img'>
    <input type="text" v-model="question" id="a"><br/>
    {{question}}
    {{ans}}
  </div>
</template>

<script>
export default {
    name: 'YesNoApi',
    data(){
      return{
          title:"INDESICION",
          question:"",
          img: "",
          ans: ""      
      }
    },
    methods: {
    async callApi(){
       const api = await fetch('https://yesno.wtf/api')
       const data = await api.json();
      console.log(data);
      this.img = data.image;
      this.ans = data.answer;
      }
    },
    watch: {
      question (value, oldValue){
      console.log(value, oldValue);
      this.question.includes('?')? this.callApi(): null
      }

    } 
 }

</script>

<style scoped> 

div{
    background-color: #dbd8ff;
    color: #877df9;
    text-align: left;
    font-size: 16px;
    font-family: helvetica
    }
#input {
  width: 30%;
  background-color: #edebff;
  color: #877df9;
  padding: 18px 20px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
</style>