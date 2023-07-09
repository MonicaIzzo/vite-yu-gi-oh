<script>
import { store } from '../data/store'
import BaseSelect from './BaseSelect.vue';


export default {
    // logica qui
    components: { BaseSelect },
    data() {
        return { store }
    },
    emits: ['type-change'],
    methods: {
        onTypeChange(types) {
            this.$emit('type-change', types);

        }
    }

};
</script>



<template>
    <header>
        <div class="filter">
            <BaseSelect v-if="store.types.length" defaultLabel="Tutti i tipi" :options="store.types"
                @option-change="onTypeChange" />
        </div>
    </header>
</template>




<style lang=" scss" scoped></style>
