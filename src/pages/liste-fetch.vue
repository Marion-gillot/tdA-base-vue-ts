<script setup lang="ts">
import Card from '@/components/card.vue';
const res = await fetch ("/maisons-public.json");
const maisons = await res.json();
</script>

<template>
<div class="p-2">
    <h1 class="text-2xl">Page Liste</h1>
    <FicheOffreMaison v-for="maison in maisons" :key="maison.nom" v-bind="maison" />
    <card class="w-1/2" v-bind="maisons"/>
</div>
</template>


