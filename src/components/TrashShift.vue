<script setup>
import { computed, defineProps } from "vue";
import { trash } from '../data/shifts.json';

const props = defineProps({ date: String });

const trashShift = computed(() => {
  const date = new Date(props.date);
  const dayOfTheWeek = date.getDay();
  return trash[dayOfTheWeek].join(', ');
});
</script>

<template>
  Turni della spazzatura: {{ trashShift }}
</template>