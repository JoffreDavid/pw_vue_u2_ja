<template>
    <Pregunta/>
</template>

<script>
    import Pregunta from "@/components/Pregunta.vue"
export default {
    components: {
        Pregunta,
    },
};
</script>

<style>
    /* Aqui puedo crear el estilo de mi componente Pregunta por herencia*/ 
    .contenedor_pregunta {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>