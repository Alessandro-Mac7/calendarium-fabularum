<script setup>
import calendarium from '@/assets/data/calendarium.json'
import {computed} from "vue";
import { useRouter } from 'vue-router';

const router = useRouter()

const months = computed( () => calendarium.map(c => c.month))

function pushRoute(route) {
  const selectedMonth = "selected-month/" + route;
  router.push(selectedMonth);
}

</script>

<template>
  <div class="container grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 ">
      <base-button class=" m-auto" v-for="(m,index) in months" v-bind:key="index" :title=m @click="pushRoute(m)"/>
  </div>
</template>

<style scoped>

</style>
