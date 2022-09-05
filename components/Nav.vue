<template>
  <nav
    class="flex justify-center items-center fixed mx-auto top-0 sm:top-0 sm:h-20 px-2 right-0 sm:right-1 gap-5 sm:rounded-lg sm:w-auto w-full dark:bg-green-900 bg-green-100 sm:ml-2"
  >
    <div
      class="hidden sm:flex justify-start items-start p-2 font-mono rounded-3xl dark:bg-green-900 bg-primary-light leading-6 dark:text-white text-black text-xs md:text-lg sm:mx-auto mx-5"
    >
      <span class="italic text-yellow-400 font-semibold uppercase">Francis-</span
      ><span
        class="font-extrabold text-blue-400 italic tracking-wide leading-6 uppercase font-mono hover:ease-in-out transition-all duration-500 transform hover:shadow-xl hover:scale-y-110"
      >
        Mwaniki</span
      >
    </div>
    <!-- Navigation Links -->
    <div
      class="md:flex justify-end items-center md:space-x-2 gap-2 dark:text-black text-black md:px-4 hidden md:uppercase lowercase p-title"
    >
      <div
        class="md:flex justify-end items-end md:space-x-2 gap-2 dark:text-black text-black md:px-4 hidden md:uppercase lowercase p-title"
        v-for="nav in navs"
        :key="nav.DirName"
      >
        <span
          ><img :src="nav.Nimg" class="h-10 w-10 p-1 dark:text-white text-black" alt=""
        /></span>
        <Nuxt-Link
          :to="nav.href"
          class="cursor-pointer dark:text-white text-black font-mono"
          >{{ nav.DirName }}</Nuxt-Link
        >
      </div>
      <span> <ToggleMode /></span>
    </div>
    <!--  TODO Mobile VUE -->
    <div class="flex sm:hidden justify-start" @click="toggleMenu = !toggleMenu">
      <div
        class="fixed flex justify-end items-end top-0 right-0 text-white bg-primary-dark p-2 m-1 rounded-full"
        v-if="!toggleMenu"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5 fill-white"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
            clip-rule="evenodd"
          />
        </svg>
      </div>
      <div
        class="fixed flex justify-end items-end top-0 right-0 m-1 dark:text-white text-black dark:bg-black bg-primary-light p-2 rounded-full"
        v-else
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
            clip-rule="evenodd"
          />
        </svg>
      </div>
      <div v-if="toggleMenu" class="flex justify-center flex-col">
        <div
          v-for="nav in navs"
          class="flex justify-center flex-col h-24 dark:text-white text-black w-full top-0 gap-0 relative z-20 p-2 m-3"
          :key="nav.DirName"
        >
          <div class="flex justify-start flex-row items-start">
            <div class="">
              <img
                :src="nav.Nimg"
                class="h-10 w-10 p-1 dark:text-white text-black"
                alt=""
              />
            </div>
            <Nuxt-Link :to="nav.href" class="mt-2 font-mono uppercase">{{
              nav.DirName
            }}</Nuxt-Link>
          </div>
        </div>
      </div>
      <div v-else=""></div>
    </div>
  </nav>
</template>

<script>
import { ref } from "vue";
import feather from "feather-icons";
export default {
  props: ["toggleMenu"],
  setup() {
    const feather = require("feather-icons");
    let navs = ref([
      {
        href: "/",
        DirName: "Home",
        Nimg: require("@/assets/images/homei.png"),
      },
      {
        href: "/AboutMe",
        DirName: "About Me",
        Nimg: require("@/assets/images/abouti.png"),
      },
      {
        href: "/work/Projects",
        DirName: "Work Projects",
        Nimg: require("@/assets/images/project.png"),
      },
      {
        href: "/ContactMe",
        DirName: "Contact Me",
        Nimg: require("@/assets/images/contacti.png"),
      },
    ]);

    return { navs, feather };
  },
  mounted() {
    feather.replace();
  },
  components: {},
};
</script>

<style></style>
