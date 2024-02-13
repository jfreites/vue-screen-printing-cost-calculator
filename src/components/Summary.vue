<template>
    <div class="section flex-child">
        <p>Print costs per shirt</p>
        <h3>${{ total }}</h3>
        <div class="separator"></div>
        <p>Labor: ${{ labor }}</p>
        <p>Art work: $0.00</p>
        <p>Film: $0.00</p>
        <p>Ink costs: $0.00</p>
        <p>Screens: $0.00</p>
        <p>Set up: $0.00</p>
        <p>Post labor: $0.00</p>
        <p>Overhead: $0.00</p>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    total: {
        type: Number,
        required: true,
    },
    labor: {
        type: Number,
        required: true,
    }
})
</script>