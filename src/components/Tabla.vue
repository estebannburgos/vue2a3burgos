<template>
    <div class="mt-5">
      <h2>Tabla de Cursos</h2>
      <table class="table">
        <thead>
          <tr>
            <th scope="col">Nombre</th>
            <th scope="col">Apellido</th>
            <th scope="col">Edad</th>
            <th scope="col">Email</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="curso in data" :key="curso.email">
            <td>{{ curso.nombre }}</td>
            <td>{{ curso.apellido }}</td>
            <td>{{ curso.edad }}</td>
            <td>{{ curso.email }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      data: {
        type: Array,
        default: () => [],
      },
    },
  };
  </script>
  