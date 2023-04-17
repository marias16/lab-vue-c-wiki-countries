<script setup>
import CountryBorders from './CountryBorders.vue'
import countriesData from '/public/countries.json'
import {ref, watch} from 'vue'
import { useRoute } from 'vue-router';

const route = useRoute()
const alpha3Code = ref(route.params.alpha3Code)

const countries = countriesData.map(country => {
    const {name,alpha2Code, alpha3Code, capital, area, borders} = country;
    return {
        name,
        alpha2Code,
        alpha3Code,
        capital,
        area,
        borders
    }
})

const country = ref(countries.find(ctr => ctr.alpha3Code === alpha3Code.value))

watch(route, (newRoute) => {
  country.value = countries.find(ctr => ctr.alpha3Code === newRoute.params.alpha3Code);
});


</script>

<template>
        <div class="col-7">
            <img :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`" alt="country flag" style="width: 50px"/>
            <h1>{{country.name.common}}</h1>
            <table class="table">
              <thead></thead>
              <tbody>
                <tr>
                  <td style="width: 30%">Capital</td>
                  <td>{{country.capital[0]}}</td>
                </tr>
                <tr>
                  <td>Area</td>
                  <td>
                    {{ country.area }} km <sup>2</sup>
                  </td>
                </tr>
                <tr>
                  <td>Borders</td>
                  <td>
                    <ul>
                      <CountryBorders v-for="border in country.borders" :key="border" :border="border"/>
                    </ul>  
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
</template>

<style scoped>
</style>