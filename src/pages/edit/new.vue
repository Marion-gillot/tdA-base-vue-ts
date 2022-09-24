<script setup lang="ts">
    import card from "../../components/card.vue";
    import FormulaireOffreMaison from "../../components/FormulaireOffreMaison.vue"

    const maisonex = {nom:"test", price:2010, favoris:false, txt:"texte", nbbath:6, nbsize:"test m²", img:"../../../public/maison1.jpg"};
</script>

<template>
    <div class="p-2">
        <h1 class="text-2xl">Page New</h1>

        <cardoffre class="w-1/3" v-bind="maisonex"/>

        <FormulaireOffreMaison class="w-1/2"/>
    </div>
    </template>