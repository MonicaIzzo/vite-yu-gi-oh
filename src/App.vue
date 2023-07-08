<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import { store } from './data/store.js'
import CharactersList from './components/CharactersList.vue';

export default {
    name: 'Yu Gi Oh',
    components: { CharactersList },

    created() {
        axios.get(endpoint)
            .then(res => {
                store.characters = res.data.docs;
            });
    }
};
</script>

<template>
    <CharactersList />
</template>

<style></style>
