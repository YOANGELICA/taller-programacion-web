<template>
    <input @keypress.enter="addQuote()" type="text" v-model="newMessage">
    {{newMessage}}

    <ul>
        <li v-for="(quote,index) in items">
            <span> {{index+1}}. {{quote.mensaje}} </span>

            <span v-if="quote.author"> Por {{quote.author}}</span>
            <span v-else> No Author </span>                        
            <span v-show="quote.edad"> Por {{quote.author}}</span> 
        </li>
    </ul>
</template>

<script>
    export default {
        name: "Directives",
        data(){
            return {
                newMessage: "",
                items: [
                    {mensaje: "Foo", author: "Juan"},
                    {mensaje: "Bar", author: "Pedro"}
                ]
            }
        },
        methods: {
            addQuote(){
                return this.items.unshift({mensaje: this.newMessage});
            }
        }
     }
</script>