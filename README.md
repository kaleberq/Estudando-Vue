Aula 13: Computed method

metodo computado X Metodo normal
o metodo computado e executado apenas uma ves e o metodo normal executa 105 vezes, assim o computado é mais rapido.
       <ul>
        <li v-for="registro in registros">
           {{registro.titulo}} - {{registro.descricao}} - {{registro.link}} - {{registro.valor | TratarValor}}
        </li>
       </ul>
       <p>Total (methods): {{ValorTotal() | TratarValor}}</p>
       <p>Total (computed): {{ValorTotalComputado | TratarValor}}</p>
       <p> contaMethods: {{contaMethods}}</p>
       <p> contaComputed: {{contaComputed}}</p>



       <script type="text/javascript">
       var app = new Vue({


             el: "#app",
             
             data: {
                 meuTitulo: "Esse é meu titulo",
                 registros: [
                     { titulo: 'Titulo 1', descricao: 'Descrição 1', link: 'delicia.com', valor: 23.048 },
                     { titulo: 'Titulo 2', descricao: 'Descrição 2', link: 'delicia.com', valor: 28.654},
                     { titulo: 'Titulo 3', descricao: 'Descrição 3', link: 'delicia.com', valor: 34 }
                 ],
                 contaMethods: 0,
                 contaComputed: 0,
             },
             filters: {
                 TratarValor: function (valor) {
                     return ('R$ ' + (valor).toFixed(2)).replace('.', ',')
                 }
             },

             methods:{
                ValorTotal: function() {
                    this.contaMethods++;
                    var total=0;
                    for(item of this.registros){
                        total += item.valor;
                    }
                   return total;

                }
             },
             computed:{
                ValorTotalComputado: function(){
                    this.contaComputed++;
                    var total=0;
                    for(item of this.registros){
                        total += item.valor;
                    }
                    return total;
                }
             }


             

             

                          })
</script>
