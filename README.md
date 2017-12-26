Em JS "" e '' é a mesma coisa

Aula 1: 

Vue e um framework progrecivo de JS.
Pode ser integrado com facilidade em outros projetos.
E uma estrutura para contrução de views para usuarios.

Aula 2:

<div id="app">{{msg}}</div> --> renderizar variaveis

<script type="text/javascript">

var app = new Vue({
Configurações do objeto
el:"#app", --> atributo do objeto
data:{--> criar vairaveis dentro do objeto
msg:'Iniciando com VUe JS'
}
})

</script>

Aula 3: Diretiva v-bind

<p title="Quando passar o mouse dobre o texto ira aparacer essa mensagem">
Teste com titulo</p>

tornar atributo html em algo dinamico onde pode alterar a informação, usar uma variavel para manipular a informação.
deve se usar a diretiva v-bind:title.
<p v-bind:title="titulo> Teste com titulo"</p>

<script type="text/javascript">

var app = new Vue({
el:#app,
data{--> usado para criar variaveis do objeto
msg:'Iniciando com Vue JS',
titulo:"Teste com V-bind"
}

)}

</script>

Aula 4: Condicional if e laço de repetção

<div id="app">
<p v-if="condição"> Teste com IF</p>
<p v-for="registro<-- *variavel que vai receber os objetos* in registros">{{registro.titulo}}</p>
</div>

<script type="text/javascript">

var app = new Vue({
el:#app,
data:{
msg:"",
titulo:"",
condicao: true
registros: [-- receber um aray
{titulo:'registro1'},-->em cada objeto vou ter um
{titulo:'registro2'},
{titulo:'registro3'},
{titulo:'registro4'},
{titulo:'registro5'}, 
]
}

)}

</script>

Aula 5: Interações e métodos

manipular eventos com vue

<button v-if="!clicou" v-on:click="usuarioClicou">Salvar</button>
<button v-if="clicou" v-on:click="usuarioClicou">aguarde...</button>

var app = new Vue({

ell: "#app",
data:[
clicou: false
],
methods:{
usuarioClicou: function (){  <-- metodo que esta recebendo uma função
   this.clicou = !this.clicou; <-- altera estado 
}
}
)}

Aula 6: Diretiva v-model

Foi criado um input, e ao digitar nele iria o objeto usuario.nome iria receber o que 
estava sendo digitado e um texto na tela ira aparecer o que foi digitado.

         <p>     
            <input type="text" v-model="usuario.nome" />
         </p>
         <p>Nome: {{usuario.nome}}</p>

         var app = new Vue({

           
             el: "#app",
             data: {
                 usuario: {nome:""}
             }
           
                          })
Aula 7: Trabalhando com components

Criar components para reaproveitamento de codigo
Ter um arquivo externo para se colocar compoents para reutilização dos mesmos
sintaxe para criar components
usasse a palavra reservada vue e o metodo para definir determinado component

 <div id="app">
       <gui-titulo></gui-titulo>

   </div>
 <script type="text/javascript">
        
        Vue.component('gui-titulo', {
            template: '<h2>Componente de titulo</h2>'
        });
         var app = new Vue({


             el: "#app"
             

             

                          })

    </script>

Aula 8: Personalizando components com props

Deixa component Dinamico, passar algumas informações na hora que o componente for usado.
Mandar paramentro com props

 <div id="app">
       <gui-titulo titulo="Esse é meu titulo"></gui-titulo>

 </div>

<script type="text/javascript">
        
        Vue.component('gui-titulo', {
            props: ['titulo'],
            template:'<h2>{{titulo}}</h2>'
            
        });
         var app = new Vue({


             el: "#app"
             

             

                          })

    </script>

Aula 9: Props dinâmicos

passar parâmetros dinâmicos para os componentes

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="TelaAdminisrativa.css">
    <title>Tela administrativa</title>
    <script src="https://unpkg.com/vue"></script>
</head>
<body>
   <div id="app">
       <gui-titulo v-bind:titulo="meuTitulo"></gui-titulo>
       <input v-model="meuTitulo"/>

   </div>

    <script type="text/javascript">
        
        Vue.component('gui-titulo', {
            props: ['titulo'],
            template:'<h2>{{titulo}}</h2>'
            
        });
         var app = new Vue({


             el: "#app",
             data: {
                 meuTitulo:"Esse é meu titulo"
             }
             

             

                          })

    </script>


</body>

</html>
