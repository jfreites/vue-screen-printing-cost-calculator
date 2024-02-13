<template>
  <Header />
  <div class="flex-container">
    <div class="section flex-child">
      <PrintSettings @printSettingsUpdated="handlePrintSettingsUpdated" />
      <LaborSettings :totalItems="totalItems" />
      <ArtworkSettings :totalFilms="totalColors" :totalItems="totalItems" />
    </div>
    <div class="section flex-child">
      <Summary :total="total" :labor="1.20" />
    </div>
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import LaborSettings from './components/LaborSettings.vue';
import PrintSettings from './components/PrintSettings.vue';
import ArtworkSettings from './components/ArtworkSettings.vue';
import Summary from './components/Summary.vue';

import { ref, computed } from 'vue';

const printSettings = ref({
  items: 10,
  colors: 1,
  locations: 1,
});

const handlePrintSettingsUpdated = (printSettingsData) => {
  printSettings.value = printSettingsData;
}

const totalItems = computed(() => {
  return printSettings.value.items;
});

const totalColors = computed(() => {
  return printSettings.value.colors;
});

const total = computed(() => {
  return 0;
});
</script>
