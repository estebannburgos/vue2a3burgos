<template>
    <div class="container mt-5">
      <div class="row justify-content-center">
        <div class="col-md-6">
          <form @submit.prevent="submitForm">
            <div class="mb-3">
              <label for="nombre" class="form-label">Nombre</label>
              <input v-model="formData.nombre" type="text" class="form-control" id="nombre" required>
              <!-- Agrega aquí las validaciones para el nombre -->
            </div>
  
            <div class="mb-3">
              <label for="apellido" class="form-label">Apellido</label>
              <input v-model="formData.apellido" type="text" class="form-control" id="apellido" required>
              <!-- Agrega aquí las validaciones para el apellido -->
            </div>
  
            <div class="mb-3">
              <label for="edad" class="form-label">Edad</label>
              <input v-model="formData.edad" type="number" class="form-control" id="edad" required>
              <!-- Agrega aquí las validaciones para la edad -->
            </div>
  
            <div class="mb-3">
              <label for="email" class="form-label">Email</label>
              <input v-model="formData.email" type="email" class="form-control" id="email" required>
              <!-- Agrega aquí las validaciones para el email -->
            </div>
  
            <div class="mb-3">
              <label>Cursos</label>
              <div>
                <div class="form-check">
                  <input v-model="formData.cursos" type="checkbox" class="form-check-input" value="Vue Js">
                  <label class="form-check-label">Vue Js</label>
                </div>
                <div class="form-check">
                  <input v-model="formData.cursos" type="checkbox" class="form-check-input" value="React">
                  <label class="form-check-label">React</label>
                </div>
                <!-- Agregar más checkboxes para otros cursos -->
              </div>
            </div>
  
            <button type="submit" class="btn btn-primary">Enviar</button>
          </form>
        </div>
      </div>
      <Tabla :data="formData.cursos" />
    </div>
  </template>
  
  <script>
  import Tabla from './Tabla.vue';
  
  export default {
    components: {
      Tabla,
    },
    data() {
      return {
        formData: {
          nombre: '',
          apellido: '',
          edad: '',
          email: '',
          cursos: [],
        },
        formState: {},
      };
    },
    methods: {
      submitForm() {
        this.formData.cursos.push({
          nombre: this.formData.nombre,
          apellido: this.formData.apellido,
          edad: this.formData.edad,
          email: this.formData.email,
        });
        this.formData.nombre = '';
        this.formData.apellido = '';
        this.formData.edad = '';
        this.formData.email = '';
      },
    },
  };
  </script>
  