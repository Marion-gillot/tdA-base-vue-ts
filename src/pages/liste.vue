<script setup lang="ts">
import Card from "../components/card.vue";
import maisons from "../assets/maisons.json";

</script>
    

<template>
  <div class="p-9">
    <h1 class="text-2xl pb-9">Page Liste</h1>
      <Card v-for="maison in maisons" :key="maison.nom" v-bind="maison" />
  </div>
</template>


