<script setup>
import CountryRouterlink from './CountryRouterlink.vue'
import countriesData from '/public/countries.json'
import { RouterView } from "vue-router";


            

const countries = countriesData.map(country => {
    const {name,alpha2Code, alpha3Code} = country;
    return {
        name,
        alpha2Code,
        alpha3Code
    }

})
</script>

<template>
    <div class="col-5" style="max-height: 90vh; overflow: scroll">
        <div class="list-group">
            <CountryRouterlink 
                v-for="item in countries" 
                :key="item.alpha3Code" 
                :alphatwo="item.alpha2Code.toLowerCase()" 
                :name="item.name.common" 
                :alphathree="item.alpha3Code"/>
        </div>
    </div>
    <RouterView />
</template>

<style scoped>
</style>