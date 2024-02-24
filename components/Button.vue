<template>
  <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-3xl"
    @click="handleClick"
  >
    {{ text }}
  </button>
</template>

<script lang="ts" setup>
const props = defineProps({
  text: {
    type: String,
    required: true,
  },
  handleClick: {
    type: Function,
    required: true,
  },
});
</script>

<style></style>
