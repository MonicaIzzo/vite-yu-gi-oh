<script>
import { computed } from 'vue';
import { colorMap } from '/src/data';

export default {
    props: {
        name: String,
        imageUrl: String,
        number: Number,
        type1: String
    },
    computed: {
        bgColor() {
            return colorMap[this.type1];
        }
    }
};
</script>


<template>
    <div class="character-card" :style="`background-color: ${bgColor}`">
        <!-- era concettualmente più corretto come in lezione
        aveva suggerito un mio collega, il colore dovevo andarlo a prendere nell'API e settare con quella una classe -->
        <div class="images">
            <img :src="imageUrl" :alt="name" :title="name">
        </div>

        <p class="number">{{ number }}</p>
        <h5 class="name">{{ name }}</h5>
        <p class="type1"><em>{{ type1 }}</em></p>


    </div>
</template>

<style lang="scss" scoped>
.character-card {
    background-color: aqua;
    padding: 1rem;
    height: 300px;
    color: white;
}

.character-card .images {
    width: 150px;
    height: 150px;
    margin: 0 auto;
    margin-bottom: 1rem;
}


img {
    display: block;
    border-radius: 50%;
    width: 100%;
    height: 100%;
    object-fit: cover;
}
</style>