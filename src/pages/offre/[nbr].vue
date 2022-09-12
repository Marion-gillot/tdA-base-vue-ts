<script setup lang="ts">
import FicheOffreMaisonVue from '@/components/FicheOffreMaison.vue';
import maisons from "../../assets/maison.json";
import FicheOffreMaison from "../../components/FicheOffreMaison.vue"; // a corriger 
defineProps < ( nbr: string ) >();
</script>

<template>
    <div class="p-2">
        <FicheOffreMaison v-bind="maisons[Number(nbr)]"  />
    </div>
</template>