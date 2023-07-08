<script>
export default {
    props: {
        name: String,
        image: String,
        number: Number,
        type1: String
    }
};
</script>


<template>
    <div class="character-card">
        <img url="https://img.pokemondb.net/artwork/large/bulbasaur.jpg" alt="Bulbasaur">
        <div class="number">1</div>
        <div class="name">Nome</div>
        <div class="type1">type</div>


    </div>
</template>

<style></style>