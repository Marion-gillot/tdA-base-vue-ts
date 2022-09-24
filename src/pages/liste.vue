<script setup lang="ts">
import card from "../components/card.vue";
//import maisons from "../assets/maisons.json";

</script>
    

<template>
  <div class="p-2">
    <h1 class="text-2xl pb-9">Page Liste</h1>
    <div v-for="maison in maisons" :key="maison.nom" v-bind="maison">
      <Card class="w-1/2" v-bind="maison" />
    </div>
  </div>
</template>


