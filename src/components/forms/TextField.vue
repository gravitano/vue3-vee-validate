<script setup lang="ts">
import { useField } from "vee-validate";

const props = defineProps<{
  name: string;
  label?: string;
  rules?: string
}>()

const { value, errorMessage } = useField(props.name, props.rules);
</script>

<template>
  <div>
    <label :for="name">{{ label }}</label>
    <input :id="name" type="text" v-model="value" v-bind="$attrs" />
    <div>{{ errorMessage }}</div>
  </div>
</template>

<style scoped>

</style>