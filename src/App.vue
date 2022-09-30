<template>
  <nav class="justify-center pt-8 pb-8">
    <ul class="flex space-x-9 justify-center">

      <li>
        <router-link class="text-black" to="/simple">
          Simple
        </router-link>
      </li>
      <li>
        <router-link class="text-black" to="/liste">
          Liste
        </router-link>
      </li>
      <li>
        <router-link class="text-black" to="/liste-fetch">
          Liste-fetch
        </router-link>
      </li>
      <li>
        <router-link class="text-black" to="/liste-supabase">
          Liste-supabase
        </router-link>
      </li>
      <li>
        <router-link class="text-black" to="/connexion">
          Se connecter
        </router-link>
      </li>
    </ul>
  </nav>

  <!-- Affiche les pages -->
  <suspense>
   <router-view class="m-2 border-2 p-2" />
  </suspense>
</template>

<script setup lang="ts">
import { Bars3Icon } from '@heroicons/vue/20/solid'
</script>
