<template>
  <div class="dark:bg-ternary-dark bg-gray-300">
    <div class=""><Loading /></div>
    <div class="relative z-20 sm:p-20 p-8 inset-0">
      <Contact />
    </div>
  </div>
</template>

<script>
import Contact from "~/components/Contact.vue";

export default { components: { Contact } };
</script>

<style></style>
