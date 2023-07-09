<script>
export default {
    props: {
        name: String,
        imageUrl: String,
        number: Number,
        type1: String
    }
};
</script>


<template>
    <div class="character-card">
        <div class="images">
            <img :src="imageUrl" :alt="name">
        </div>

        <p class="number">{{ number }}</p>
        <h5 class="name">{{ name }}</h5>
        <p class="type1">{{ type1 }}</p>


    </div>
</template>

<style lang="scss" scoped>
.character-card {
    background-color: aqua;
    padding: 1rem;
    height: 300px;
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