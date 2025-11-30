<template>
  <div>
    <label for="id_nombre">Nombre: </label>
    <input v-model="nombre" id="id_nombre" type="text" />
    <p>{{ nombre }}</p>

    <label for="id_apellido">Apellido: </label>
    <input v-model="apellido" id="id_apellido" type="text" />
    <p>{{ apellido }}</p>

    <button v-on:click="imprimirNombre()">Imprimir Nombre</button>
    <button v-on:click="agregarEstudiante()">agregarEstudiante</button>

    <h1>Lista</h1>
    <ul>
      <li
        v-show="nombre !== null"
        v-for="{ nombre, apellido } in arreglo"
        :key="nombre"
      >
        {{ nombre }} {{ apellido }}
      </li>
    </ul>

    <table border="1">
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Apellido</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-show="nombre !== null"
          v-for="{ nombre, apellido } in arreglo"
          :key="nombre"
        >
          <td>{{ nombre }}</td>
          <td>{{ apellido }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nombre: null,
      apellido: null,
      arreglo: [],
    };
  },
  methods: {
    imprimirNombre() {
      console.log(this.nombre);
    },
    agregarEstudiante() {
      const estu = {
        nombre: this.nombre,
        apellido: this.apellido,
      };
      console.log("Se agreta estudiante");
      console.log(estu);
      this.arreglo.push(estu);
      this.limpiarFormulario();
    },
    limpiarFormulario() {
      this.nombre = null;
      this.apellido = null;
    },
  },
};
</script>

<style>
</style>