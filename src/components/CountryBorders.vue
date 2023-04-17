<script setup>
import { defineProps, toRefs} from 'vue'
import { RouterLink } from "vue-router";
import countriesData from '/public/countries.json'

const props = defineProps({
    border: String,

})

const { border } = toRefs(props);

const countries = countriesData.map(country => {
    const {alpha3Code, name} = country;
    return {
        name,
        alpha3Code
    }
});


const countryElement = countries.find((country) => country.alpha3Code === border.value);
const countryName = countryElement.name.common


</script>

<template>
    <li><RouterLink :to="`/list/`+ border">{{ countryName }}</routerlink></li> 
</template>

<style>
</style>