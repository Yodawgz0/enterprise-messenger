<script setup lang="ts">
import { ref, watch } from 'vue';
import { RouterLink, RouterView, useRoute } from 'vue-router'

const buttonText = ref("")
const route = useRoute()

watch(
  () => route.path,
  (to,) => {
    // Check the path and change the button text
    if (to === '/login') {
      buttonText.value = 'Sign Up';
    } else if (to === '/signup') {
      buttonText.value = 'Login';
    } else if (to === "/") {
      buttonText.value = "dashboard"
    }
  },
  { immediate: true }
);

</script>

<template>
  <header>
    <div class="wrapper ">

      <nav v-if="buttonText !== 'dashboard'" class=" bg-black text-yellow-200 flex flex-row-reverse">

        <RouterLink class="me-6 mt-6 bg-orange-950 px-4 py-1 rounded-lg"
          :to="buttonText === 'Login' ? '/login' : '/signup'">{{ buttonText }}</RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
</template>

<style scoped></style>
