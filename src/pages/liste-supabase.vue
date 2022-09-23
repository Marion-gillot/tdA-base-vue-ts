<script setup lang="ts">
import { supabase } from "../supabase";
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code
const maisons = []; // à remplacer par l'appel à Supabase
</script>

<template>
<div class="p-2">
    <h1 class="text-2xl">Liste</h1>
    <FicheOffreMaison v-for="maison in maisons" :key="maison.nom" v-bind="maison" />
    <card class="w-1/2" v-bind="maisons"/>
</div>
</template>


