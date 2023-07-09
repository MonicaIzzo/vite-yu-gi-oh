<script>
export default {
    props: {
        options: Array,
        defaultLabel: String
    }

};
</script>

<template>
    <select>
        <option value="">{{ defaultLabel || '---' }}</option>
        <option v-for="option in options" :key="option">{{ option }}</option>
    </select>
</template>

<style></style>