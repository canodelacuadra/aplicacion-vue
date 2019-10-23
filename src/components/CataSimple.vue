<template>

  <div id="cata">
   <h3>{{cataSimple.nombre }}</h3>
  <p>{{cataSimple.descripcion}}</p>
   <p>{{cataSimple.precio}}</p>
<b-button variant="success" v-b-modal="'my-modal'">Enviar Reserva</b-button>

  
   
  </div>
</template>
<script>

  export default {
 name: 'CataSimple',
  props:{
        cataSimple: Array,
    },components: {
  
    
    
    },

   
  }
</script>

<style scoped></style>