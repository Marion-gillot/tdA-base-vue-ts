<script setup lang="ts">
import bath from "./icones/bath.vue";
import heart from "./icones/heart.vue";
import Bed from "./icones/bed.vue";
import Size from "./icones/size.vue";

defineProps ({
    price: {
      type: Number,
      default: 2700,
    },
    favoris: {
      type: Boolean,
      default: false,
    },
    nom: {
      type: String,
      default: "Beverly Springfield",
    },
    txt: {
      type: String,
      default: "2821 Lake Sevilla, Palm Harbor, TX",
    },
    img: {
      type: String,
    },
    nbbath: {
      type: String,
      default: "5 Bathrooms",
    },
    nbsize: {
      type: String,
      default: "6x7.5 m²",
    },
    nblit: {
      type: String,
      default: "2 Beds",
    }
});
</script>

<template>
  <figure class="m-6">
    <!-- Pour changer la valeur d'un attribut on utilise un "binding" :
    https://vuejs.org/guide/essentials/template-syntax.html#attribute-bindings 
    Ici on affecte à l'attribut 'src' la 'props' "image" -->
    <img class="w-full h-48 object-cover" src="public/maison1.jpg" alt="maison" />
     <figcaption
      class="relative flex flex-col rounded-b-lg border-2 border-t-0 px-5 py-7"
    >
      <h3 class="text-2xl text-gray-900">{{ nom }}</h3>
      <address class="not-italic text-gray-500">{{ txt }}</address>
      <div class="order-first flex items-center">
        <div class="text-2xl text-indigo-500">
          ${{ price.toLocaleString("en-US") }}
        </div>
        <div class="text-gray-500">/mois</div>
      </div>
      <hr class="my-2 border-t-2 border-indigo-100" />
      <div class="flex justify-between text-sm">
        <div><bed class="inline-block align-top" /> {{ nblit }}</div>
        <div><bath class="inline-block align-top" /> {{ nbbath }}</div>
        <div><size class="inline-block align-top" /> {{ nbsize }}</div>
      </div>
      <div
        class=" absolute top-7 right-4 grid h-12 w-12 place-items-center rounded-full border-2 border-indigo-100">
        <heart :class="{ 'fill-indigo-500': favoris }" />
      </div>
    </figcaption>
  </figure>
</template>