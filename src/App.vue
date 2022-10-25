<script setup>
import { ref } from "vue";
import TrashShift from './components/TrashShift.vue';
import StreetShift from './components/StreetShift.vue';

const date = ref("");
</script>

<template>
  <header>
    <h1>Turni</h1>
  </header>

  <main>
    Data: <input type="date" v-model="date" />
    <TrashShift :date="date" v-if="date" />
    <StreetShift :date="date" v-if="date" />
  </main>
</template>
