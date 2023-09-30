<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper ">
      <nav class=" bg-black text-yellow-200 flex flex-row-reverse">
        <RouterLink class="me-6 mt-6 bg-orange-950 px-4 py-1 rounded-lg" to="/signup">Sign up</RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
</template>

<style scoped></style>
