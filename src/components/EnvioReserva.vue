<template>
  <div>
    <form name="contact" method="POST" data-netlify="true">
  <p>
    <label> Nombre <input type="text" name="name" /></label>   
  </p>
  <p>
    <label>Email: <input type="email" name="email" /></label>
  </p>
  <p>
    <label>Cata: <select name="role[]" multiple>
      <option value="Cata 3 vinos">Cata de tres vinos</option>
      <option value="Cata 5 vinos">Cata de cinco vinos</option>
    </select></label>
  </p>
  <p>
    <label>Observaciones: <textarea name="message"></textarea></label>
  </p>
  <p>
    <button type="submit">Enviar Reserva</button>
  </p>
</form>
  </div>
   
</template>

<script>
  export default {
  
  }
</script>

<style scoped>
 
</style>