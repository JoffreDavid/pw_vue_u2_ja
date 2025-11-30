<template>
  <div>
    <h1>{{ tit }}</h1>
    <p>{{ numero }} <sup>2</sup>={{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>2</sup>={{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>2</sup>={{ calcularCuadrado }}</p>
    <p>{{ numero }} <sup>3</sup>={{ calcularCubo }}</p>
    <p>{{ numero }} <sup>3</sup>={{ obtenerCubo() }}</p>
  
    <button @:click="incrementar()">+1</button>
    <button @:click="decrementar()">-1</button>
    <button v-show="mostrar">Prueba</button>
  </div>

</template>

<script>
export default {
  data() {
    return {
      numero: this.inicio,
      titulo: "contador",
      exp: 2,
    };
  },

  methods: {
    obtenerCuadrado() {
      console.log("Entro a obtenerCuadrado:");
      return this.numero * this.numero;
    },

    obtenerCubo() {
      console.log("Entro a obtenerCuadrado:");
      return this.numero * this.numero * this.numero;
    },
    incrementar() {
      console.log(this.tit);
      this.numero++;
    },
    decrementar() {
      console.log(this.tit);
      this.numero--;
    },
  },
  computed: {
    calcularCuadrado() {
      console.log("Entro a propiedad computada:");
      return this.numero * this.numero;
    },

    calcularCubo() {
      console.log("Entro a propiedad computada:");
      return this.numero * this.numero * this.numero;
    },
  },
  /**String, Number, Boolean, Array, Object, Date, Funcion, BigInt */
  /*props: ["tit","inicio","mostrar"], Declaracion basica de props*/
  props: {
    tit: String,
    inicio: {
      type: Number,
      default: 99,
      validator(value) {
        return value>10;
      },
    },
    mostrar: Boolean,
  },
};
</script>

<style>
</style>
