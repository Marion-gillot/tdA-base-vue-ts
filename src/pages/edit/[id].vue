<script setup lang="ts">
    import FormulaireOffreMaison from "@/components/FormulaireOffreMaison.vue"
    defineProps (["id"]);

    
</script>


<template>
    <div class="p-9">
        <FormulaireOffreMaison :id="id" />
    </div>
</template>