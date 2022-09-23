<script setup lang="ts">
import { ref } from "@vue/reactivity";
import card from "@/components/card.vue";
import listeSupabaseVue from "@/pages/liste-supabase.vue";
// On fait une variable réactive qui réference les données
// ATTENTION : faire une Ref pas une Reactive car :
// c'est l'objet qui doit être réactif, pas ses props
const maison = ref({});
const props = defineProps (["id"]);
if (props.id) {
        //Chargement des données de la maison 
        let { data, error } = await listeSupabase
        .from("Maison")
        .select("*")
        .eq("id", props.id);
    if ( error ) console.log("n'a pas pu charger la table Maison:", error);
    else maison.value = ( data as any[]) [0];
}

async function upsertMaison(dataForm, node) {
        const { data, error } = await supabase.from("Maison").upsert(dataForm);
        if (error) node.setErrors([error.message]);
        else {
                node.setErrors([]);
                router.push ({ name: "nom", params: { id: dataForm,
                id } });
        }
}
</script>


<template>
    <div>
        <div class="p-2">
        <h2 class="text-2xl">Résultat (Prévisualisation)</h2>

        //Optionnel on affiche les données 
        <Card v-bind="maison" />
     </div>
        <div class="p-2">

//On passe la "ref" à FormKit

<FormKit type="form" v-model="maison" 
    :submit-attrs="{ classes: { input: 'bg-red-300 p-1 rounded' } }"
    :config="{  classes: {
                input: 'p-1 rounded border-gray-300 shadow-sm border',
                label: 'text-gray-600',
        },
        }">

<FormKit name="nom" label="nom"/>
<FormKit name="prix" label="prix" type="number"/>
<FormKit name="favori" label="mettre en valeur" type=" checkbox" />
<FormKit
 name="favori"
 label="mettre en valeur"
 type="checkbox"
 wrapper-class="flex"
  />
</FormKit>
</div>
</div>
</template>