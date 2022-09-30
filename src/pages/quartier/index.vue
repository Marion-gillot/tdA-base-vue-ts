<script setup lang="ts">
 const { data, error } = await supabase.from("quartiercommune"),
select("")

</script>

<template>

    <li v-for="quartierObjecr in listeQartier"
    :key="quartierObject.codeQuartier">
    </li>
<RouterLink
  :to="{
    name: 'quartier-id',
    params: { id: quartierObject.code_Quartier },
  }"
>{{ quartierObject.libelle_Quartier }}</RouterLink>
</template>

