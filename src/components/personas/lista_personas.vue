<script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8=" crossorigin="anonymous">
</script>
<script src="/static/dist/semantic.js"></script>

<template lang="html">

 <div class="container">
   <div class="row">
     <div class="col text-left">
       <h2>Lista de personas</h2>

       <div class="columns medium-3" v-for="persona in personas" style="border-style: solid;border-color: coral;">
         <div class="card">
           <div class="card-divider">
             {{ persona.nombre }}
           </div>
           <div class="card-section">
             <p>{{ persona.apellido }}.</p>
           </div>
         </div>
       </div>

       <div style="border-style: solid;border-color: coral;">ssssss</div>
      
      

       <div class="dimension-list-item" style="border-style: solid;border-color: coral;">
              ccccccccccccccccccc
       </div>



</div>
</div>
</div>

</template>

<script>
   import axios from 'axios';
   export default {

       data() {
           return {
               fields: [{
                   key: 'nombre',
                   label: 'nombre'
               }, {
                   key: 'apellido',
                   label: 'apellido'
               }, {
                   key: 'action',
                   label: 'Acciones'
               }],
               personas: []
           }
       },
       methods: {
           getPersonas() {
               const path = 'http://127.0.0.1:8000/api/v1/personas/'
               axios.get(path).then((response) => {
                       this.personas = response.data.results
                   })
                   .catch((error) => {
                       console.log(error)
                   })
           }
       },

       created() {
           this.getPersonas()
       },
   }
</script>

