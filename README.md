Aula 11: v-once v-html

v-once corta ligação entre variavel ou seja mesmo que seja alterado 
o valor não ira mudar na exibição do v-once.

v-html lê o valor de uma váriavel como codigo html e não como um texto.

<div id="app">

       <gui-titulo v-bind:titulo="meuTitulo"></gui-titulo>

       <input v-model="meuTitulo"/>

       <gui-tabela v-bind:titulos="['Nome','E-mail','Link do cachorro']" v-bind:registros="registros"></gui-tabela>
       <p v-once>{{meuTitulo}}</p>
       <p v-html="html"></p>
       

   </div>

 <script type="text/javascript">
        
        

         var app = new Vue({


             el: "#app",
             data: {
                 meuTitulo: "Esse é meu titulo",
                 html:'<a href="#"> Esse é um link </a>'
             }
             

             

                          })

    </script> 
