<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
export default {
    data() {
        return {
            docs: [],
            characters: []
        }
    },
    created() {
        axios.get(endpoint)
            .then(res => {
                this.characters = res.data.results;
            });
    }
};
</script>




<template>
    <div class="container text-center">
        <div class="row row-cols-5 g-4 ">
            <div class="col" v-for="character in characters" :key="character.id">
                <CharacterCard :name="character.name" :image="character.imageUrl" :number="character.number"
                    :type1="character.type1" />
            </div>
        </div>
    </div>
</template>

<style></style>