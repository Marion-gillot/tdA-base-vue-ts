<script setup lang="ts">
import Card from "../components/card.vue";
const maison0 = {
        name:'maison 1',
        prix:'4300€',

    };
</script>


<template>
    <h4 class="mt-8 mb-8 font-bold text-center">Offre Maison</h4>
    <Card :prix="50"/>

    <Card  v-bind="maison0"/>


</template>


<style scoped>

</style>