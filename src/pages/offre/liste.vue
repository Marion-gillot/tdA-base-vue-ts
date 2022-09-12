<script setup lang="ts">
import Card from "../components/card.vue";

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
    
<Card v-for="maison in maisons" :key="" v-bind="maison"/>





    
</script>
    

<template>

</template>


<style scoped>
</style>
