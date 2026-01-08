<template>
    <div class="pokemon_container">
        <img :src="srcImagen" 
        alt="No se puede renderizar">
    </div>
    
</template>

<script>
export default {
    props: {
        pokemonId: {
            type: Number,
            requiered: true,
        }
    },
    computed: {
        srcImagen(){
            return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${this.pokemonId}.svg`;
        }
    }
}
</script>

<style scoped>
img {
    height: 200px;
    right: 32%;
}
.pokemon_container{
    height: 200px;
    display: flex;
    justify-content: center;
}
</style>