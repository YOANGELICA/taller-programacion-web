<template>
    <div>
        <h1>¿Aprobado o reprobado?</h1>
        <input type="text" v-model="student.name" placeholder="Nombre del estudiante" id="name"><br/>
        <input type="number" v-model="student.grade1" placeholder="Nota 1" class="a" min=0>
        <input type="number" v-model="student.grade2" placeholder="Nota 2" class="a" min=0>
        <input type="number" v-model="student.grade3" placeholder="Nota 3" class="a" min=0><br/>
        <button @click="getAvg()" id="btn"> Listo! </button>
        <h1>{{student.name}}, {{student.status}}</h1>
    </div>
</template>


<script>
  export default{
    name: 'Nota',
    data(){
      return {
        student:{
            name: '',
            grade1: '',
            grade2: '',
            grade3: '',
            avg: '',
            status: ''
        }

      }
    },
    methods:{
        getAvg(){
            this.student.avg = (parseFloat(this.student.grade1)+parseFloat(this.student.grade2)+parseFloat(this.student.grade3))/3;
            this.student.avg = this.student.avg.toFixed(2);
            if(this.student.avg >= 3){
                this.student.status = 'aprobado/a'
            }
            else if(this.student.avg < 3, this.student.avg >= 0){ 
                this.student.status = 'reprobado/a'
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
    font-family: Helvetica
    }
    #name{
  width: 35%;
  background-color: #fffae9;
  color: #ffb27a;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
.a{
  width: 18%;
  background-color: #fffae9;
  color: #ffb27a;
  padding: 15px 15px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
#btn{
    width: 15%;
  background-color: #ffb27a;
  color: #fffae9;
  padding: 15px 15px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: pointer;
  font-weight: 800;
}
    ::placeholder {
    color: #ebcea5;
    font-size: 1em;
    font-style: italic;
}
</style>