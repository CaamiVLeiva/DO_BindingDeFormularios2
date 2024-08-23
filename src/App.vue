<template>
  <div id="app" class="container-fluid d-flex justify-content-center align-items-center min-vh-100 p-3">
    <div class="row w-100">
      <div class="col-md-4 mb-4">
        <FormularioIngreso :formData="formData" @update:formData="updateFormData" />
      </div>
      <div class="col-md-8 mb-4">
        <VistaPrevia
          :titulo="formData.titulo"
          :emoji="formData.emoji"
          :apreciacion="formData.apreciacion"
          :competencias="formData.competencias"
          :opinion="formData.opinion"
        />
      </div>
    </div>
  </div>
</template>

<script>
import FormularioIngreso from './components/FormularioIngreso.vue';
import VistaPrevia from './components/VistaPrevia.vue';

export default {
  name: 'App',
  components: {
    FormularioIngreso,
    VistaPrevia,
  },
  data() {
    return {
      formData: {
        titulo: 'Estoy aprendiendo Vue Js',
        emoji: '😊',
        apreciacion: 'Increíble',
        competencias: [],
        opinion: 'Ahora podré desarrollar aplicaciones más cómodamente!!',
      },
    };
  },
  methods: {
    updateFormData(newFormData) {
      this.formData = { ...this.formData, ...newFormData };
    },
  },
};
</script>

<style scoped>
#app {
  height: 100vh;
  background-color: #e9ecef;
}
</style>
