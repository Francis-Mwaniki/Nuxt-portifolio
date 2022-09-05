<template>
  <div class="max-w-4xl sm:max-w-full dark:bg-black bg-gray-100">
    <Loading />
    <!-- Main Nav -->
    <div class="relative z-30"><Nav :toggleMenu="toggleMenu" /></div>
    <div>
      <Nuxt />
    </div>
  </div>
</template>

<script>
import Nav from "~/components/Nav.vue";
import { ref } from "vue";
export default {
  setup() {
    let toggleMenu = ref(false);
    return { toggleMenu };
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();
      setTimeout(() => this.$nuxt.$loading.finish(), 5000);
    });
  },
  components: { Nav },
};
</script>

<style>
/* ::-webkit-scrollbar {
  width: 5px;
  height: 3px;
  border-left: 1px solid brown;
}
::-webkit-scrollbar-thumb {
  background-color: var(--main-red);
}
::-moz-scrollbar {
  width: 5px;
  height: 3px;
  border-left: 1px solid brown;
}
::-moz-scrollbar-thumb {
  background-color: var(--main-red);
} */
body {
  overflow-x: hidden !important;
}
</style>
