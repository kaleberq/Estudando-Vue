Em JS "" e '' é a mesma coisa

Aula 10: Exemplo de componente de Tabela.


<body>
   <div id="app">

       <gui-titulo v-bind:titulo="meuTitulo"></gui-titulo>

       <input v-model="meuTitulo"/>

       <gui-tabela v-bind:titulos="['Nome','E-mail','Link do cachorro']" v-bind:registros="registros"></gui-tabela>

       

   </div>

    <script type="text/javascript">
        
        Vue.component('gui-titulo', {
            props: ['titulo'],
            template:'<h2>{{titulo}}</h2>'
            
        });

        Vue.component('gui-tabela', {
            props: ['titulos', 'registros'],
            template:

            '<table style="width:100%">'+
                '<thead>'+
                    '<tr>'+
                        '<th v-for="titulo in titulos">{{titulo}}</th>'+
                        
                    '</tr>'+
                '</thead>'+
                '<tbody>'+
                    '<tr v-for="registro in registros">'+
                        '<td v-for="item in registro">{{item}}</td>'+
                    '</tr>'+
                '</tbody>'+

            '</table>'

        });

         var app = new Vue({


             el: "#app",
             data: {
                 meuTitulo: "Esse é meu titulo",
                 registros: [
                     { titulo: 'Titulo 1', descricao: 'Descrição 1', link: 'delicia.com' },
                     { titulo: 'Titulo 2', descricao: 'Descrição 2', link: 'delicia.com' },
                     { titulo: 'Titulo 3', descricao: 'Descrição 3', link: 'delicia.com' }
                 ]
             }
             

             

                          })

    </script>


</body>
