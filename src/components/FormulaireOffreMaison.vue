<script setup lang="ts">
import { ref } from "@vue/reactivity";
import card from "@/components/card.vue";
import listeSupabaseVue from "@/pages/liste-supabase.vue";
import { supabase } from "@/supabase";
// On fait une variable réactive qui réference les données
// ATTENTION : faire une Ref pas une Reactive car :
// c'est l'objet qui doit être réactif, pas ses props
const maison = ref({nom:"test", price:29, favoris:false, txt:"test", nbbath:4, nblit:3, nbsize:"45 m²", img:"../../public/maison1.jpg"});
/* const props = defineProps (["id"]);
if (props.id) {
        //Chargement des données de la maison 
        let { data, error } = await listeSupabase
        .from("Maison")
        .select("*")
        .eq("id", props.id);
    if ( error ) 
    console.log("n'a pas pu charger la table Maison:", error);
    else maison.value = data [0];
} */

async function upsertMaison(dataForm, node) {
        const { data, error } = await supabase.from("Maison").upsert(dataForm);
        if (error) node.setErrors([error.message]);
       /*  else {
                node.setErrors([]);
                router.push ({ name: "nom", params: { id: dataForm,
                id } });
        } */
}
</script>


<template>
    <div>
        <div class="p-2">


<!-- Optionnel on affiche les données -->
        <card v-bind="maison" />
     </div>
        <div class="p-2">

<!-- On passe la "ref" à FormKit -->

 <FormKit @submit="upsertMaison"
  type="form" v-model="maison"
            :config="{
                        classes: {
                                    input: 'p-1 rounded border-gray-300 shadow-sm border bg-bg-text-gray-600 hover:bg-border-gray-300 hover:border-4 hover:animate-pulse',
                                    label: 'text-gray-600',
                                },
                    }"
            :submit-attrs="{ classes: { input: 'bg-text-gray-600 px-6 py-2 rounded-full text-center' } }">
                <FormKit name="nom" label="Nom"/>
                <FormKit name="txt" label="Description"/>
                <FormKit name="price" label="Prix" type="number"/>
                <div class="flex gap-5">
                    <FormKit name="nbsize" label="Superficie"/>
                    <FormKit name="nblit" label="Nombre de lit" type="number"/>
                    <FormKit name="nbbath" label="Nombre de Salle de bains" type="number"/>
                </div>
                <FormKit name="favoris" label="mettre en valeur" type="checkbox" wrapper-class="flex gap-4"/>
            </FormKit>
</div>
</div>
</template>