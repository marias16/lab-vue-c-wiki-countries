<script setup>
import CountryBorders from './CountryBorders.vue'
import {ref} from 'vue'

const alpha3Code = ref(route.params.alpha3Code)
const country = ref(null)
//cogeremos el alpha3code, lo matchearemos con el json y cogeremos el pais 

</script>

<template>
    <router-view>
        <div class="col-7">
            <img :src="`https://restcountries.eu/data/` + country.alpha2Code + `.svg`" alt="country flag" style="width: 300px"/>
            <h1>{{country.name}}</h1>
            <table class="table">
              <thead></thead>
              <tbody>
                <tr>
                  <td style="width: 30%">Capital</td>
                  <td>{{ country.capital }}</td>
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
                      <CountryBorders v-for="border in borders" :border="border"/>
                    </ul>  
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
    </router-view>
</template>

<style scoped>
</style>