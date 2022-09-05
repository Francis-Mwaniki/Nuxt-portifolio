<template>
  <div class="dark:bg-ternary-dark bg-gray-300 dark:text-black text-base">
    <Loading />
    <div class="relative z-20 sm:p-20 p-8 inset-0">
      <About />
    </div>
  </div>
</template>

<script>
import About from "~/components/About.vue";
export default { components: { About } };
</script>

<style></style>
