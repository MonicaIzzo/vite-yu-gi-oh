<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';

import { store } from './data/store.js'
import CharactersList from './components/CharactersList.vue';
import AppHeader from './components/AppHeader.vue';

export default {
    name: 'Pokemon',
    components: { CharactersList, AppHeader },
    methods: {
        filterPokemon(types) {
            console.log(types);

        },

        fetchTypes() {
            axios.get(endpoint + '/types1')
                .then(res => {
                    store.types = res.data;
                });
        },

    },

    created() {
        axios.get(endpoint)
            .then(res => {
                store.characters = res.data.docs;
            });
        this.fetchTypes();
    },
};
</script>

<template>
    <!--Header con filto ricerca -->
    <AppHeader @type-change="filterPokemon" />
    <!--Card Pokemon -->
    <CharactersList />
</template>

<style lang="scss"></style>
