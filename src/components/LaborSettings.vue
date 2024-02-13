<template>
    <div class="settings-section">
        <p class="settings-title">Labor</p>

        <div class="input-group">
            <label>Hourly wage</label>
            <input type="text" v-model="hourlyWage">
        </div>

        <div class="input-group">
            <label>Items per hour</label>
            <input type="text" v-model="itemsPerHour">
        </div>

        <p>Total items {{ totalItems }}</p>
        <p>Hours needed {{ hoursNeeded }} hours</p>
        <p>Labor costs ${{ laborCosts }}</p>
        <p>Costs per shirt ${{ costsPerShirt }}</p>
    </div>
</template>

<script setup>
import { ref, computed, defineProps } from 'vue';

// TODO: remember to use Maska package for apply mask to inputs

// inputs
const hourlyWage = ref('12.5');
const itemsPerHour = ref('45'); // 45/hr using a mask for this

// props
const props = defineProps({
    totalItems: {
        type: Number,
        required: true,
    },
})

// computed props
const hoursNeeded = computed((totalItems) => {
    //return '0.22';
    return props.totalItems / itemsPerHour.value;
});

const laborCosts = computed(() => {
    //return '2.78';
    return hourlyWage.value * hoursNeeded.value;
});

const costsPerShirt = computed(() => {
    // return '0.28'
    return laborCosts.value / props.totalItems;
});
</script>