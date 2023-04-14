<script setup>
import { defineProps } from 'vue'

defineProps({
    border: {
        type: String,
    }
})
</script>

<template>
    <li><routerlink :to="`/list/`+ border">{{ border }}</routerlink></li> //poner el common name
</template>

<style>
</style>