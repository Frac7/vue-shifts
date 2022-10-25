<script setup>
import { computed } from "vue";
import { trash } from "../data/shifts.json";

const props = defineProps({ date: String });

const trashShift = computed(() => {
  const date = new Date(props.date);
  const dayOfTheWeek = date.getDay();
  return (trash[dayOfTheWeek] || ["-"]).join(", ");
});
</script>

<template>
  <div class="flex-1 text-center bg-sky-400/25 w-full p-8 rounded-2xl">
    <span class="text-white m-8">Turni della spazzatura: </span
    ><span class="text-sky-500">{{ trashShift }}</span>
  </div>
</template>
