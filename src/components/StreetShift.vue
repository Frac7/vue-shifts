<script setup>
import { computed, defineProps } from "vue";
import { street } from '../data/shifts.json';

const props = defineProps({ date: String });

const streetShift = computed(() => {
  const date = new Date(props.date);
  const dayOfTheWeek = date.getDay();
  return street[dayOfTheWeek];
});
</script>

<template>
  Turni della lavastrada: {{ streetShift }}
</template>