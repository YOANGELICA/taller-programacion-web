<template>
    <Div>
        <h1>¿Aprobado o reprobado?</h1><br/>
        <input type="text" v-model="name" placeholder="Nombre" class="a"><br/>
        <input type="number" v-model="grade1" placeholder="Nota 1" class="a" min=0><br/>
          <p v-if="grade1<=5">
            <input type="number" v-model="grade2" placeholder="Nota 2" class="a" min=0><br/>
          </p>
          <p v-else> La nota máxima es 5</p>
          <p v-if="grade2<=5">
              <input type="number" v-model="grade3" placeholder="Nota 3" class="a" min=0><br/>
          </p>
          <p v-else> La nota máxima es 5</p>
            <button @click="addstudent()" id="botoncito"> Agregar Estudiante </button><br/>
          <ul>
            <li v-for="(student,index) in students" >
              <span>{{student.status}}</span> 
            </li>
          </ul>
    </Div>
</template>


<script>
  export default{
    name: 'Notas',
    data(){
      return {
        name:'',
        grade1:'',
        grade2:'',
        grade3:'',
        avg:'',
        stadus:'',
        students:[],
        student:{
            name: '',
            grade1: '',
            grade2: '',
            grade3: '',
            avg: '',
            status: ''
        },
        }
      },
      methods: {
        addstudent(){
          this.avg = (parseFloat(this.grade1)+parseFloat(this.grade2)+parseFloat(this.grade3))/3;
          this.students.push({
            name: this.name,
            grade1: this.grade1,
            grade2: this.grade2,
            grade3: this.grade3,
            avg: this.avg,
            status: this.avg >= 3 ? `${this.name}: Ganó la materia`: `${this.name}: Perdió la materia`
          });
          this.name = '';
          this.grade1 ='';
          this.grade2 = '';
          this.grade3 = '';
          this.avg = '';
          this.status = '';
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
    .a{
  width: 30%;
  background-color: #edebff;
  color: #877df9;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
#botoncito{
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