<script setup lang="ts">
</script>

<template>
  <main>
    <div class=" bg-black flex flex-col h-screen ">
      <p class="text-center mt-20 text-yellow-100 text-4xl font-semibold">Login Page!</p>
      <div class="p-8 mx-96 flex flex-col justify-evenly mt-20">
        <div class="flex flex-row font-bold justify-evenly mb-5 ">
          <p class="text-yellow-400">Username :</p>
          <input class="border-solid border-2 rounded-lg text-center" />
        </div>
        <div class="flex flex-row font-bold justify-evenly ">
          <p class="text-yellow-400">Password :</p>
          <input type="password" class=" border-solid border-2 rounded-lg text-center" />
        </div>
        <button class="mt-11 bg-yellow-600 rounded-md py-1 w-64 font-bold ms-56">Login</button>
      </div>
    </div>
  </main>
</template>

<style scoped></style>