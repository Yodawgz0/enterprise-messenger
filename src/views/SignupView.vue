<script setup lang="ts">
import { ref, type Ref } from 'vue';
import axios from "axios";
import router from '@/router';
import type { user } from './Props';

const userName: Ref<string> = ref("")
const password: Ref<string> = ref("")

const loginHandler = () => {
  const userDetails: user = {
    username: userName.value,
    password: password.value
  }
  axios
    .post("http://localhost:8000/signup", {
      userDetails,
    })
    .then(function (response) {
      console.log(response);
      router.push("/login");
    })
    .catch(function (error) {
      if (error.response!.status === 409) {
        alert(error.response.data.message)
        router.push("/login");
      }
    });
}
</script>

<template>
  <main class=" bg-black h-[95.5vh]">
    <div class="flex flex-col ">
      <p class="text-center mt-20 text-yellow-100 text-4xl font-semibold">Sign Up Page!</p>
      <div class="p-8 mx-96 flex flex-col justify-evenly mt-20">
        <div class="flex flex-row font-bold justify-evenly mb-5 ">
          <p class="text-yellow-400">Username :</p>
          <input v-model="userName" class="border-solid border-2 rounded-lg text-center" />
        </div>
        <div class="flex flex-row font-bold justify-evenly ">
          <p class="text-yellow-400" ref="passwordInput">Password :</p>
          <input v-model="password" type="password" class=" border-solid border-2 rounded-lg text-center" />
        </div>
        <button @click="loginHandler" class="mt-11 bg-yellow-600 rounded-md py-1 w-64 font-bold ms-56">Sign Up</button>
      </div>
    </div>
  </main>
</template>

<style scoped></style>