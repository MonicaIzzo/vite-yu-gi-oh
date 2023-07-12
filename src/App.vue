<script>
import axios from 'axios';
let endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';

import { store } from './data/store.js'
import CharactersList from './components/CharactersList.vue';
import AppHeader from './components/AppHeader.vue';


export default {
    name: 'Pokemon',
    components: { CharactersList, AppHeader },
    methods: {


        // Questa funzione non va, va rivista.        
        filterPokemon(types) {
            const uri = endpoint + `?eq[type1]=${types}`;
            console.log(uri);
            endpoint = uri;
            console.log(endpoint);
            axios.get(endpoint)
                .then(res => {
                    store.characters = res.data.docs;
                });
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
