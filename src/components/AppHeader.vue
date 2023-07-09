<script>
import { types } from '../data';
export default {
    // logica qui
    props: {
        defaultLabel: String,
        options: Array
    }
};
</script>


<template>
    <select name="" id="">
        <option value="">{{ defaultLabel || '--' }}</option>
        <option v-for="option in options" :key="option">Opzion3 1</option>
    </select>
</template>


<style lang="scss" scoped></style>