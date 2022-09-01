<template>
    <h1> {{customTitle}} </h1> <br/>
    <h3> {{counterNumber}} * {{counterNumber}} = {{getMultiplication}} </h3> <br/>
    <button @click="increase"> +1 </button> <br/>
    <button @click="decrease"> -1 </button> <br/>
    <button id= "reset" @click="reset"> Reset </button> 
    <span>{{counterNumber}}</span>
</template>

<script>
    export default {
      props: ["title"],
      name: 'Counter',
      data(){
        return{
          counterNumber: 5,
          title1: this.title
        }
      },
      methods: {
        increase() {
          this.counterNumber ++;
        },
        decrease(){
          this.counterNumber --;
        },
        reset(){
          this.counterNumber = 5;
        }
      },
      computed: {
        getMultiplication(){
          console.log('calling method');
          return this.counterNumber * this.counterNumber
      },
        customTitle(){
          // console.log(this.title1);
          // if (typeof this.title1 === 'undefined'){
          //   return this.title1 = "My counter";
          //   }else {
          // return this.title1
          return this.title || "My counter"; //forma mas facil de hacer esas condiciones
            }
          }  
       }

</script>

<style scoped>
  button {
        text-align: center;
        background-color: #e8e6ff;
        border: none;
        color:  #8880e8;
        padding: 10px 10px;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        border-radius: 24px;
  }

  /* los ids se llaman con # y las clases con . */

      #reset {
        background-color: #8880e8; /* todo queda igual, solo especifico estas dos cosas */
        color:  #e8e6ff;
  }

</style>
