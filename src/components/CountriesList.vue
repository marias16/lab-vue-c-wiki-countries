<script setup>
import CountryRouterlink from './CountryRouterlink.vue'
</script>

<template>
    <CountryRouterlink v-for="item in countries" :alpha2Code="item.alpha2Code.toLowerCase()" :name="item.name.common" :alpha3Code="item.alpha3Code"/>
    <router-view />
</template>

<style scoped>
</style>