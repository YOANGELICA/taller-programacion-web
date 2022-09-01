<template>
  <div> 
      <h1>Create a table!</h1>
      <input type="number" v-model="columns" class="a" placeholder="Columnas" min="0">
      <br>
      <input type="number" v-model="rows" class="a" placeholder="Filas" min="0">
        <p v-if="columns > 0 && rows > 0">
          <table>
            <tbody>
              <tr v-for="row in rows">
                <td v-for="col in columns">{{col}},{{row}}</td>
              </tr>
            </tbody>
          </table>
        </p>
  </div>
</template>

<script>
export default {
  name: 'Tabla',
  data(){
      return{
          columns :'',
          rows: ''
      }
  }
}

</script>

<style scoped>
  div{
background-color: #d5f1b5;
color: #8ac447;
text-align: center;
font-size: 16px;
font-family: helvetica
}
table {
font-family: 'Open Sans', sans-serif;
width: 750px;
border-collapse: collapse;
border: 3px solid #75aa39;
margin: 10px 10px 0 10px;
}

table th {
text-transform: uppercase;
text-align: left;
background: #75aa39;
color: #FFF;
padding: 8px;
min-width: 30px;
}

table td {
text-align: left;
padding: 8px;
border-right: 2px solid #75aa39;
}
table td:last-child {
border-right: none;
}
table tbody tr:nth-child(2n) td {
background: #b9e08c;
color: #699c2f
}
.a{
  width: 32%;
  background-color: #e8fbd2;
  color: #699c2f;
  padding: 15px 30px;
  margin: 10px 0;
  border: none;
  border-radius: 24px;
  cursor: text;
}
::placeholder {
  color: #afca8f;
  font-size: 1em;
  font-style: italic;
}

</style>