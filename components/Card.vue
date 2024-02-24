<template>
  <div class="relative">
    <div class="absolute inset-0">
      <div
        class="bg-blue-500 rounded-tr-xl rounded-bl-xl shadow-md p-4 min-w-fit"
      >
        <div class="flex items-center space-x-4">
          <Icon :name="iconName" class="w-8 h-8 text-slate-900" />
          <h3 class="text-lg text-slate-900">
            {{ title }}
          </h3>
        </div>
      </div>
    </div>
    <div class="relative z-10 translate-x-2 -translate-y-2">
      <div class="bg-white rounded-tr-xl rounded-bl-xl shadow-md p-4 min-w-fit">
        <div class="flex items-center space-x-4">
          <Icon :name="iconName" class="w-8 h-8 text-slate-400" />
          <h3 class="text-lg text-slate-900">
            {{ title }}
          </h3>
        </div>
      </div>
      <div
        class="absolute inset-0 ring-1 ring-inset ring-slate-500 rounded-tr-xl rounded-bl-xl"
      ></div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps({
  iconName: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
});
</script>

<style></style>
