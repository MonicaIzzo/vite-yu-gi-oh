<script>
import { store } from '../data/store'
import BaseSelect from './BaseSelect.vue';
import { types } from '../data';


export default {
    // logica qui
    components: { BaseSelect },
    data() {
        return store
    }

};
</script>


<template>
    <header>
        <div class="filter">
            <BaseSelect defaultLabel="Tutti i tipi" />
        </div>
    </header>
</template>


<style lang="scss" scoped></style>