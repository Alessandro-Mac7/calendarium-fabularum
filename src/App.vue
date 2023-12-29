<script setup>
import CalendarHome from "@/views/CalendarHome.vue";
import { useRouter } from 'vue-router';

const router = useRouter()

function homeClick() {
  router.push("/");
}
</script>

<template>
  <header class="text-center">
    <h1 class="mt-5 title clickable brown" @click="homeClick">Calendarium fabularum</h1>
    <h3 class="mb-10 lighter sub-title">Tό μυθικόν ἡμερολογεῖον</h3>
  </header>

  <router-view v-slot="{ Component }">
    <transition name="scale" mode="out-in">
      <component :is="Component"/>
    </transition>
  </router-view>
</template>

<style scoped>

.title {
  font-family: 'DistilleryDisplay', sans-serif;
  font-size: 3rem;
}

.sub-title {
  font-family: 'Bosk', sans-serif;
  font-size: 1.8rem;
}
</style>
