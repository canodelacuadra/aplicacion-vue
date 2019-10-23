<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Dirección de email:"
        label-for="input-1"
        description="
Nunca compartiremos su correo electrónico con nadie más"
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          type="email"
          required
          placeholder="Introduzca  email"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="Nombre del responsable:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.name"
          required
          placeholder="Introduzca el nombre"
        ></b-form-input>
      </b-form-group>
        <b-form-group id="input-group-6" label="Número de personas:" label-for="input-6">
        <b-form-input
          id="input-6"
          type="number"
          v-model="form.personas"
          required
        ></b-form-input>
      </b-form-group>
       <b-form-group id="input-group-5" label="Fecha de Reserva:" label-for="input-5">
        <b-form-input
          id="input-5"
          type="date"
          v-model="form.fecha"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-3" label="Cata:" label-for="input-3">
        <b-form-select
          id="input-3"
          v-model="form.cata"
          :options="catas"
          required
        ></b-form-select>
      </b-form-group >
     

      <b-form-group id="input-group-4">
        <b-form-checkbox-group v-model="form.checked" id="checkboxes-4">
          <b-form-checkbox value="me">Check me out</b-form-checkbox>
          <b-form-checkbox value="that">Check that out</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group>

      <b-button type="submit" variant="primary">Enviar</b-button>
      <b-button type="reset" variant="danger">Borrar</b-button>
    </b-form>
    <b-card class="mt-3" header="Resumen de la Reserva">
      <pre class="m-0">{{ form }}</pre>
    </b-card>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          email: '',
          name: '',
          personas:'',
          fecha:'',
          cata: null,
          checked: []
        },
        catas: [{ text: 'Selecciona una', value: null }, 'Cata de tres vinos', 'Cata de cinco vinos', 'Cata cinco vinos top', 'Cata de quesos y aceites'],
        show: true
      }
    },props:{
     
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Borramos los valores del formulario
        this.form.email = ''
        this.form.name = ''
        this.form.personas = ''
          this.form.fecha = ''
        this.form.cata = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>

<style scoped>
 
</style>