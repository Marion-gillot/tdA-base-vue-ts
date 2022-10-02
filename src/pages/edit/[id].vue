<script setup lang="ts">
    import FormulaireOffreMaison from "@/components/FormulaireOffreMaison.vue"
    import { supabase } from "@/supabase"
    defineProps ({
        id_maison : String,
    });

    
</script>


<template>
    <div class="p-9">
        <h1 class="text-2xl">Page Edit[id]</h1>
        <FormulaireOffreMaison :id="id" />
    </div>
</template>