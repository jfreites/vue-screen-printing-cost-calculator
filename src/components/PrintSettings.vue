<template>
    <div class="settings-section">
        <p class="settings-title">Print settings</p>
        <p>A print job could be had mutliples print settings per location.</p>
        <form id="print-settings-form" @submit.prevent="onSubmit">
            <div class="input-group">
                <label for="num_items"># of items</label>
                <input type="text" name="num_items" v-model="numItems">
            </div>

            <div class="input-group">
                <label for="num_colors"># of colors</label>
                <input type="text" name="num_colors" v-model="numColors">
            </div>

            <!--
            <div class="input-group">
                <label for="num_locations"># of locations</label>
                <input type="text" name="num_locations" v-model="numLocations">
            </div> -->

            <div class="btn-holder">
                <button class="btn">Update</button>
            </div>
        </form>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const numItems = ref(10);
const numColors = ref(1);
//const numLocations = ref(1);

const emit = defineEmits(['printSettingsUpdated']);

const onSubmit = () => {
    // validate inputs

    const printSettingsData = {
        items: parseInt(numItems.value),
        colors: parseInt(numColors.value),
        //locations: parseInt(numLocations.value)
    }

    emit('printSettingsUpdated', printSettingsData);
}
</script>