<template>
  <form
    name="ask-question"
    method="post"
    data-netlify="true"
    data-netlify-honeypot="bot-field"
    >
    <input type="hidden" name="form-name" value="ask-question" />
   <label for='nombre'>Escribe tu nombre</label>
   
    <input name ='nombre' type ='text'>
    <p>Elige tu panelista:</p>
    <label v-for="(panelist, index) in panelists" :key="index">
      <input
        type="radio"
        name="panelist"
        :value="panelist"
        @input="ev => updatePanelist"
        :checked="panelist === currentPanelist"
      />
     
      <span>{{ panelist }}</span>
      
    </label>
     <hr>
       <label for='question'>Escribe tu pregunta</label>
       <textarea name="question"></textarea>
    <br>
    <button class='btn btn-success'>Enviar</button>
  </form>
</template>
<script>
export default {
  name: "QAForm",
  methods: {
    updatePanelist (ev) {
      this.currentPanelist = ev.target.value
    }
  },
  data () {
    return {
      panelists: ['Evan You', 'Chris Fritz','Jose Cano'],
      currentPanelist: 'Evan You'
    }
  }
}
</script>

<style scoped>
 
</style>