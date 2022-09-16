<script setup lang="ts">
import Card from "../components/card.vue";
import maisons from "../assets/maisons.json";

</script>
    

<template>
  <div class="p-2">
    <h6>Page liste.vue</h6>
    <div v-for="maison in maisons" :key="maison.nom" v-bind="maison">
      <Card class="w-1/2" v-bind="maison" />
    </div>
  </div>
</template>


