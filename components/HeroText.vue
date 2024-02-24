<template>
  <div class="space-y-4">
    <TypingAnimation />
    <h1 class="text-2xl md:text-4xl text-slate-900">
      Empower your business with digital solutions!
    </h1>
    <h2 class="text-slate-400 max-w-lg">
      Say hello to game-changing solutions tailored just for you. We are here to
      unlock hidden opportunities, we've the skills to make it happen. Ready to
      take your business to next level?
    </h2>
    <div class="text-left">
      <Button text="Let's chat!" :handleClick="handleClick" />
    </div>
  </div>
</template>

<script lang="ts" setup>
const handleClick = () => {
  const recipient = "apps@brainiacapps.com";
  const subject = "Contact request from Brainiac Apps Website";
  const body =
    "Hi Brainiac Apps, I would like to discuss about your services. Can we schedule a meeting? Thanks!";
  const mailtoLink = `mailto:${recipient}?subject=${encodeURIComponent(
    subject
  )}&body=${encodeURIComponent(body)}`;

  console.log(mailtoLink);

  // Open default email client with pre-filled email in a new tab
  window.open(mailtoLink, "_blank");
};
</script>

<style></style>
