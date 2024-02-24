<template>
  <main>
    <section class="container mx-auto px-4">
      <div class="flex flex-col gap-16 justify-center items-center h-screen">
        <p>
          Oops! This page doesn't exist. Let's get you back on track – hit the
          back button.
        </p>
        <Button :handleClick="handleError" text="Back" />
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
const handleError = () => clearError({ redirect: "/" });
</script>
