
<script setup lang="ts">
import { library } from '@fortawesome/fontawesome-svg-core'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faPaperPlane } from '@fortawesome/free-solid-svg-icons'
import { ref } from 'vue';
library.add(faPaperPlane)
const chatInput = ref('');
const dataChat = ref([{ p1: 'Asdhley' }, { p1: 'Asdhley' }, { p2: 'Asdhley' }]);

function addChatMessage() {
  if (chatInput.value) {
    dataChat.value.push({ p2: chatInput.value });
    chatInput.value = '';
  }
}
</script>

<template>
  <main class="bg-black h-[100vh]">
    <p class="text-white text-center font-bold pt-4 text-2xl">EnChat</p>
    <hr class="border-yellow-600 mt-4" />
    <div class="flex flex-row">
      <div class="w-[20vw] border-2 border-black border-r-yellow-600 h-[90vh] relative">
        <div
          class="before:absolute before:content-[''] before:h-2 before:w-2 before:bg-green-400 before:rounded-full translate-x-24 translate-y-5">
        </div>
        <p class="text-white text-center p-3 pl-8 relative">
          Online Users
        </p>
        </div>
      </div>
      <div>
        <div class="h-[75vh]">
          <div class="h-[75vh]">
            <div v-for="(item, index) in dataChat" :key="index">
              <div class="flex flex-col">
                <p v-if="item.p1" class="text-white bg-red-950 rounded w-[30vw] m-3 p-3">{{ item.p1 }}</p>
                <div v-else-if="item.p2" class="flex justify-end">
                  <p class="text-white bg-amber-400 rounded w-[30vw] m-3 p-3 text-right">{{ item.p2 }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <hr class="border-2 w-[80vw] border-white" />
        <input @keyup.enter="addChatMessage" v-model="chatInput" class="mx-3 my-4 w-[70vw] rounded outline-none p-2" />
        <font-awesome-icon @click="addChatMessage" class="text-white w-6 h-6 pt-7 ms-5 cursor-pointer"
          icon="paper-plane" />
      </div>
    </div>
  </main>
</template>

<style scoped></style>