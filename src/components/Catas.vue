<template>

  <div id="lista-catas">
 <CataSimple
 v-for="cata in catas" 
 v-bind:key="cata.id"
 v-bind:cataSimple = "cata"
 
 
 ></CataSimple>
   <b-modal  id="my-modal" title="Reserva de Catas">
     <EnvioReserva/>
  </b-modal>
    
   
  </div>
</template>
<script>
import CataSimple from '@/components/CataSimple.vue'
import EnvioReserva from '@/components/EnvioReserva.vue'

  export default {
    name: 'Catas',
    components: {
    CataSimple,
      EnvioReserva,
    
    },
    props:{
        catas: Array,
    }
  }
</script>

<style scoped>
#lista-catas{
  display: flex;
  flex-wrap:wrap;
  justify-content:center;
 
}
#lista-catas div{
  width: 350px;
  padding:1em;
  border: 1px solid burlywood;
      border-color: #343a40 !important;

  

 
}

</style>