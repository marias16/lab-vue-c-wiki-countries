<script setup>
import { defineProps } from 'vue'
import { RouterLink} from "vue-router";

defineProps({
  alphathree: {
    type: String,
  },
  alphatwo: {
    type: String,
  },
  name: {
    type: String,
  },
})

</script>

<template>
    <RouterLink class="list-group-item list-group-item-action" :to="`/list/${alphathree}`">
        <img :src="`https://flagpedia.net/data/flags/icon/72x54/${alphatwo}.png`" />
        <p>{{ name }}</p>
    </RouterLink>
</template>

<style scoped>
</style>