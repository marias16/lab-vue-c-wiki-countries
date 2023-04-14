<script setup>
import { defineProps } from 'vue'

defineProps({
  alpha3Code: {
    type: String,
  },
  alpha2Code: {
    type: String,
  },
  name: {
    type: String,
  },
})

</script>

<template>
    <routerlink class="list-group-item list-group-item-action" :to="`/list/` + alpha3Code">
        <img :src="`https://flagpedia.net/data/flags/icon/72x54/` + alpha2Code `.png`" />
        <p>{{ name }}</p>
    </routerlink>
</template>

<style scoped>
</style>