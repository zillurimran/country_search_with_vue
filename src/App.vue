<script setup>
  import { ref } from 'vue';
  import {countries} from './data/country.js'
  const search = ref('')

  function getFilterContries(){
    return countries.filter(country => {
      return country.name.toLowerCase().startsWith(search.value.toLowerCase())
    })
  }
</script>

<template>
<section class="text-white">
  <p class="">{{ search }}</p>
  <p class="my-3">
    search: <input type="text" class="rounded-full p-3 ml-2 bg-gray-500" v-model="search">
  </p>
  <p class="my-2 ml-20">
    <ul class="">
      <li v-for="country in getFilterContries()" :key="country.name">
        {{ country.name }}
      </li>
    </ul>
  </p>
</section>
</template>

<style scoped>

</style>
