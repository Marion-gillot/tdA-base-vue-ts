<script setup lang="ts">
import Card from '../components/card.vue';
const objet = {nom:"Beverly Springfield", price:34, favoris:true, txt:"produit de test",  nbbath:2, nbsize:"test m²", img:"../../public/maison1.jpg"}
</script>

<template>
    <div class="p-9 ">
        <h1 class="text-2xl pb-9">Page Simple</h1>
        <Card class="w-1/2" v-bind="objet"/>
    </div>
</template>