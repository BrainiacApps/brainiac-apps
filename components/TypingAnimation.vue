<template>
  <div class="flex gap-2 md:gap-4">
    <p class="text-3xl md:text-6xl font-bold text-slate-900">Brainiac</p>
    <div>
      <span
        class="text-3xl md:text-6xl text-transparent bg-clip-text bg-gradient-to-r from-blue-500 via-teal-500 to-lime-500"
        >{{ currentTypingWord }}</span
      >
      <span class="text-3xl md:text-6xl text-lime-500 animate-ping">_</span>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed, onMounted } from "vue";

const words = ref(["apps", "data", "software", "solutions", "business"]);
const currentWordIndex = ref(0);
const currentTypingWordIndex = ref(0);
const currentWord = computed(() => words.value[currentWordIndex.value]);
const currentTypingWord = computed(() =>
  currentWord.value.substring(0, currentTypingWordIndex.value)
);
const typingSpeed = 200;
const deletingSpeed = 50;

const typeLetter = () => {
  return new Promise((resolve) => {
    let i = 0;
    const interval = setInterval(() => {
      if (i > currentWord.value.length) {
        clearInterval(interval);
        resolve();
      } else {
        currentTypingWordIndex.value = i;
        i++;
      }
    }, typingSpeed);
  });
};

const deleteLetter = () => {
  return new Promise((resolve) => {
    let i = currentWord.value.length;
    const interval = setInterval(() => {
      if (i < 0) {
        clearInterval(interval);
        resolve();
      } else {
        currentTypingWordIndex.value = i;
        i--;
      }
    }, deletingSpeed);
  });
};

const pause = (ms: number) => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, ms);
  });
};

onMounted(async () => {
  let i = 0;
  while (i < words.value.length) {
    await typeLetter();
    await pause(1500);
    await deleteLetter();
    await pause(500);
    currentWordIndex.value = (currentWordIndex.value + 1) % words.value.length;
    i++;
  }
  await typeLetter();
});
</script>

<style scoped></style>
