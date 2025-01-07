<script setup>
import { defineProps } from 'vue';

const {data}= defineProps(['data'])
</script>

<template>
<div>
    <h3>{{ data.question }}</h3>
    <p>{{ data.answer }}</p>
</div>
</template>

<style scoped>
</style>