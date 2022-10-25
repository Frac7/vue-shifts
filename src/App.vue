<script setup>
import { ref } from "vue";
import TrashShift from "./components/TrashShift.vue";
import StreetShift from "./components/StreetShift.vue";

const date = ref("");
</script>

<template>
  <header class="flex justify-center m-8">
    <h1
      class="flex-1 text-center text-sky-500 bg-sky-400/25 max-w-[50%] p-8 rounded-2xl"
    >
      Turni
    </h1>
  </header>

  <main class="m-auto max-w-[50%] flex flex-col items-center">
    <div class="flex-1 m-12">
      <span class="text-white">Data:</span>&nbsp;
      <input
        type="date"
        v-model="date"
        class="text-white bg-black border-b-[1px] border-solid border-white"
      />
    </div>
    <TrashShift :date="date" v-if="date" />
    <StreetShift :date="date" v-if="date" />
  </main>
</template>

<style scoped>
input {
  color-scheme: dark;
}
</style>
