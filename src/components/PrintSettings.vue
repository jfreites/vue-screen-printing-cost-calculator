<template>
    <div class="settings-section">
        <p class="settings-title">Print settings</p>

        <div class="input-group">
            <label for="num_items"># of items</label>
            <input type="text" name="num_items" id="num_items" :value="numItems">
        </div>

        <div class="input-group">
            <label for="num_colors"># of colors</label>
            <input type="text" name="num_colors" id="num_colors" :value="numColors">
        </div>

        <div class="input-group">
            <label for="num_locations"># of locations</label>
            <input type="text" name="num_locations" id="num_locations" :value="numLocations">
        </div>
    </div>
</template>

<script setup>
import { ref, defineExpose } from 'vue';

const name = ref("print settings");
const numItems = ref(10);
const numColors = ref(1);
const numLocations = ref(1);

defineExpose({
    name,
    numItems,
})
</script>