<script setup lang="ts">
import { supabase } from "../supabase";
import Card from "../components/Card.vue";
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code
let { data: tableauMaisons, error } = await supabase
  .from('maison')
  .select('*')
 // à remplacer par l'appel à Supabase
</script>

<template>
<div class="p-9">
    <h1 class="text-2xl">Page Liste Supabase</h1>
    <Card v-for="uneMaison in tableauMaisons" :key="uneMaison.nom" v-bind="uneMaison" />
</div>
</template>


