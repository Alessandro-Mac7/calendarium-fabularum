<script setup>
import calendarium from '@/assets/data/calendarium.json'
import {computed} from "vue";
import BaseCard from "@/components/ui/BaseCard.vue";

const props = defineProps({
  month: String
})

const currentMonth = computed( () => calendarium.find(c => c.month === props.month));

function getClass(align, fontWeight, fontStyle) {
  let cssClass = "";
  if(align) {
    cssClass += " text-" + align  + " pre-wrap";
  } else {
    cssClass += " text-" + align;
  }
  if (fontWeight) {
    cssClass += " font-" + fontWeight + " ";
  }
  if (fontStyle) {
    cssClass += " " + fontStyle;
  }

  console.log(cssClass)
  return cssClass;
}
function getImgUrl(pic){
  if(/(http(s?)):\/\//i.test(pic)) {
    return pic;
  }
  return new URL('/src/assets/images/'+pic, import.meta.url).href;
}

</script>

<template>
  <base-card>
    <header class="text-center">
      <h3 class="title mt-4 mb-2 lighter">{{currentMonth.month}}</h3>
      <h3 class="sub-title mb-4 lighter">{{currentMonth.title}}</h3>
      <img :alt="currentMonth.title" :src="getImgUrl(currentMonth.img)">
    </header>
    <main class="text-justify mb-5">
      <div v-for="(t,index) in currentMonth.texts" v-bind:key="index" class="my-5">
        <p :class='getClass(t.align, t.fontWeight, t.fontStyle)'>{{ t.text }}</p>
      </div>
    </main>
  </base-card>
</template>

<style scoped>
.title {
  font-family: 'EFCOBrookshireRegular', sans-serif;
  font-size: 2rem;
}

.sub-title {
  font-family: 'Bosk', sans-serif;
  font-size: 1.4rem;
}
</style>
