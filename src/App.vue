<template>
  <nav class="justify-center pt-8 pb-8">
    <ul class="flex space-x-9">

      <li>
        <router-link class="text-indigo-400 underline" to="/simple">
          Simple
        </router-link>
      </li>
      <li>
        <router-link class="text-indigo-400 underline" to="/liste">
          Liste
        </router-link>
      </li>
      <li>
        <router-link class="text-indigo-400 underline" to="/liste-fetch">
          Liste-fetch
        </router-link>
      </li>
    </ul>
  </nav>

  <!-- Affiche les pages -->
  <router-view class="m-2 border-2 p-2" />
</template>

<script setup lang="ts">
import { Bars3Icon } from '@heroicons/vue/20/solid'
</script>
