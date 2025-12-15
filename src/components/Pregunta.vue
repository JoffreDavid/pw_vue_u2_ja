<template>
  <div class="contendor_pregunta">
    <img v_if="imagen" :src="imagen"
      alt="No puede visualizarse"
    />

    <div class="oscuro"></div>

    <div class="pregunta_container">
      <h1>Pregunta</h1>
      <input v-model="pregunta" type="text" placeholder="Hazme una pregunta" />
      <p>Recuerdaw acabar con el signo de interrogacion (?)</p>
      <h2>Sere millonario</h2>
      <h1>Yes, No</h1>

      <h2></h2>
      <h1></h1>

    </div>
  </div>
</template>

<script>
    import { consumirAPIFacade } from '../clients/YesNoClient';

export default {
    data() {
        return {
            pregunta: null,
            respuesta: null,
            imagen: null,
        };
    },
    watch: {
        pregunta(value, oldValue){
            if(value.includes("?")) {
                this.respuesta = 'Pensando..'
                this.consumir();
            }

        },
    },
    methods: {
        async consumir(){
            const resp = await consumirAPIFacade();
            console.log('Respuesta final');
            console.log(resp);
            console.log(resp.answer);
            this.respuesta = resp.answer;
            this.imagen = resp.image;
        }
    }
};
</script>

<style scoped>
img,
.oscuro {
  height: 100vh;
  width: 100vw;
  max-height: 100%;
  max-width: 100%;
  position: fixed;
  left: 0px;
  top: 0px;
}
.oscuro {
    background-color: rgba(0, 0, 0, 0.6);
    
}
.pregunta_container {
  position: relative;
  min-height: 100vh; /* altura de toda la pantalla */
  /*color:white;*/
  display: flex;
  justify-content: center; /* centrado vertical */
  align-items: center; /* centrado horizontal */
  text-align: center;
  flex-direction: column; /* elementos uno debajo del otro */
}
input {
  width: 250px;
  padding: 10px 15px;
  border-radius: 5px;
  border: none;
}

input:focus {
  outline: none;
}

h1,
h2,
p {
  color: white;
}

p {
  font-size: 20px;
}

h2 {
  margin-top: 150px;
}
</style>