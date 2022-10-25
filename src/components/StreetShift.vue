<script setup>
import { computed } from "vue";
import { street } from "../data/shifts.json";

const props = defineProps({ date: String });

const streetShift = computed(() => {
  const date = new Date(props.date);
  const dayOfTheWeek = date.getDay();
  return street[dayOfTheWeek] || "-";
});
</script>

<template>
  <div class="flex-1 text-center bg-sky-400/25 w-full p-8 rounded-2xl m-8">
    <span class="text-white">Turni della lavastrada: </span
    ><span class="text-sky-500">{{ streetShift }}</span>
  </div>
</template>
