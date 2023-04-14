<script setup>
import CountryRouterlink from './CountryRouterlink.vue'
</script>

<template>
    <CountryRouterlink v-for="item in countries" :alpha2Code="item.alpha2Code" :name="item.name.common" :alpha3Code="item.alpha3Code"/>
</template>

<style scoped>
</style>