<script setup>
import NavBar from './components/Navbar.vue'
import { RouterView } from "vue-router";

</script>

<template>
  <div class="app">
    <NavBar />
    <div class="container">
      <div class="row">
        <RouterView />
      </div>
    </div>
  </div>
</template>


<style>

</style>