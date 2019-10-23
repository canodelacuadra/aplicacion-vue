<template>
  <div id="app" class="container">
    <Cabecera/>

    <catas :catas="catas" />
  </div>
</template>

<script>
import Cabecera from '@/components/Cabecera.vue'
  import Catas from '@/components/Catas.vue'

  export default {
    name: 'app',
    components: {
    Cabecera,
    Catas,
     
    },
    data(){
      return {
        catas: [
        {
          id: 1,
         nombre: 'Cata de tres vinos',
         descripcion: 'richard@piedpiper.com',
         precio: 12,
        },
        {
          id: 2,
         nombre: 'Cata de tres vinos con especial de caza',
          descripcion: 'gilfoyle@piedpiper.com',
          precio: 15,
        },
        {
          id: 3,
          nombre: 'Cata de cinco vinos',
          descripcion: 'dinesh@piedpiper.com',
          precio:  25,
        },
        {
          id: 4,
          nombre: 'Cata de quesos y aceites',
          descripcion: 'dinesh@piedpiper.com',
          precio:  25,
        },
      ],

      }
    },
  }
</script>

<style>

</style>
