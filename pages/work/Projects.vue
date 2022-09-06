<template>
  <main class="relative z-20 sm:pt-14 pt-8 inset-0">
    <div class="">
      <Loading />
    </div>

    <div
      class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 md:mt-6 sm:gap-10 max-w-5xl mx-auto p-2 gap-3"
    >
      <div
        class="dark:bg-green-900 bg-gray-100 p-2 rounded-md hover:ease-in-out transition-all duration-500 transform hover:shadow-md hover:scale-95 sm:hover:scale-105 sm:w-full w-auto mx-auto"
        v-for="project in projectData"
      >
        <nuxt-link :to="`/work/${project.id}`">
          <div class="relative z-20">
            <img
              :src="project.img"
              :alt="project.langProjectName"
              class="rounded-xl cursor-pointer h-3/5 w-full mx-auto"
            />
            <h1 class="font-mono font-semibold uppercase dark:text-white text-black p-1">
              {{ project.langProjectName }}
            </h1>
            <p
              class="font-serif font-light dark:text-primary-light text-primary-dark tracking-wide p-1"
            >
              {{ project.projectContent }}
            </p>
          </div>
        </nuxt-link>
      </div>
    </div>
  </main>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    return {};
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          projectData: ref([
            {
              id: 0,
              langProjectName: "MongoDB",
              projectContent: "The noSQL Database used for keepings records & documents",
              img: require("@/assets/images/mongodb.jpg"),
            },
            {
              id: 1,
              langProjectName: "NuxtJs",
              projectContent: "The no vueJs Framework used for making Universal Apps",
              img: require("@/assets/images/nuxt.jpg"),
            },
            {
              id: 2,
              langProjectName: "VueJs",
              projectContent: "The no Js Framework used for making Single Page Apps",
              img: require("@/assets/images/vuejs.jpg"),
            },
            {
              id: 3,
              langProjectName: "NodeJs",
              projectContent: "The no One Js runtime used for making servers Apps",
              img: require("@/assets/images/nodejs.png"),
            },
            {
              id: 4,
              langProjectName: "Vue Js",
              projectContent: "The vueJs project for simple questions and answer",
              img: require("@/assets/images/vuejs.jpg"),
            },
            {
              id: 5,
              langProjectName: "Ecommerce Shop",
              projectContent: "The no vueJs project used made for Ecommerce",
              img: require("@/assets/images/web-project-2.jpg"),
            },
          ]),
        });
      }, 500);
    });
  },
  components: {},
  mounted() {},
};
</script>

<style></style>
