<script>
export default {
    props: {
        defaultLabel: String
    }

};
</script>

<template>
    <select>
        <option value="">{{ defaultLabel || '---' }}</option>
        <option>opzione 1</option>
    </select>
</template>

<style></style>