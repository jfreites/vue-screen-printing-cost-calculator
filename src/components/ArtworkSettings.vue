<template>
    <div class="settings-section">
        <p class="settings-title">Art Work</p>

        <div class="input-group">
            <label for="hourly_wage">Hourly wage</label>
            <input type="text" v-model="hourlyWage">
        </div>

        <div class="input-group">
            <label for="time_per_film">Time per film</label>
            <input type="text" v-model="timePerFilm">
        </div>

        <p># films {{ totalFilms }}</p>
        <p>Hours needed {{ hoursNeeded }} hours</p>
        <p>Labor costs ${{ laborCosts }}</p>
        <p>Costs per shirt ${{ costsPerShirt }}</p>
    </div>
</template>

<script setup>
import { ref, computed, defineProps } from 'vue';

// TODO: remember to use Maska package for apply mask to inputs

// inputs
const hourlyWage = ref('14.5'); // $ 14.5
const timePerFilm = ref('1'); // 20/hr using a mask for this

// props
const props = defineProps({
    totalFilms: {
        type: Number,
        required: true,
    },
    totalItems: {
        type: Number,
        required: true,
    },
})

// computed props
const hoursNeeded = computed((totalItems) => {
    //return '0.33';
    return timePerFilm.value * props.totalFilms;
});

const laborCosts = computed(() => {
    //return '4.83';
    return hourlyWage.value * hoursNeeded.value;
});

const costsPerShirt = computed(() => {
    // return '0.48'
    return laborCosts.value / props.totalItems;
});
</script>