<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import { store } from './data/store.js'
import CharactersList from './components/CharactersList.vue';
import SearchForm from './components/SearchForm.vue';

export default {
    name: 'Pokemon',
    components: { CharactersList, SearchForm },

    created() {
        axios.get(endpoint)
            .then(res => {
                store.characters = res.data.docs;
            });
    }
};
</script>

<template>
    <SearchForm />
    <CharactersList />
</template>

<style lang="scss"></style>
