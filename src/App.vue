<script setup>
import { ref, onMounted, computed } from "vue";

import Header from './components/Header.vue'
import LaborSettings from './components/LaborSettings.vue';
import PrintSettings from './components/PrintSettings.vue';
import ArtworkSettings from './components/ArtworkSettings.vue';
import Summary from './components/Summary.vue';

const printSettings = ref();

onMounted(() => {
  console.log(printSettings.value.numItems)
  console.log(printSettings.value.name)
});
</script>

<template>
  <Header />
  <div class="flex-container">
    <div class="section flex-child">
      <PrintSettings ref="printSettings" />
      <LaborSettings />
      <ArtworkSettings />
    </div>
    <div class="section flex-child">
      <Summary />
    </div>
  </div>
</template>
