<script setup lang="ts">
import Card from "../../components/card.vue";
import maisons from "../../assets/maisons.json";
defineProps < { nbr: string } >();
</script>

<template>
    <div class="p-2">
        <FicheOffreMaison v-bind="maisons[Number(nbr)]" />
    </div>
</template>