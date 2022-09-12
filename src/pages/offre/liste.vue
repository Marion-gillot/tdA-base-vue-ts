<script setup lang="ts">
import cardVue from "../../components/card.vue";

const maisons = [{
  nbrSDB: '4',
  nom: 'Maison',
  prix:'45€',
  favori: '7',
},
{
    nbrSDB: '4',
    nom: 'Maison',
    prix: '45€',
    favori: '7',
}];
    
</script>
    

<template>
  <div class="p-2">
    <h6>Page liste.vue</h6>
    <div v-for="maisons in maisons" :key="maisons.nom">
      <Card class="w-1/2" v-bind="maisons" />
    </div>
  </div>
</template>


