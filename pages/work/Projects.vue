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
        :key="project.langProjectName"
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
    let projectData = ref([
      {
        id: 0,
        langProjectName: "VueJs",
        projectContent:
          "A   js framework for building universal Apps Maybe you can try it out!!",
        img: require("@/assets/images/mobile-project-1.jpg"),
      },
      {
        id: 1,
        langProjectName: "NuxtJs",
        projectContent:
          "A vue js framework for building universal Apps Maybe you can try it out!!!",
        img: require("@/assets/images/mobile-project-2.jpg"),
      },
      {
        id: 2,
        langProjectName: "Js",
        projectContent:
          "A cross platform programming language Maybe you can try it out!!",
        img: require("@/assets/images/ui-project-1.jpg"),
      },
      {
        id: 3,
        langProjectName: "Pinia",
        projectContent: "A vue js new State Management Maybe you can try it out!!",
        img: require("@/assets/images/web-project-1.jpg"),
      },
      {
        id: 4,
        langProjectName: "NodeJs",
        projectContent: "A backend runtime env Maybe you can try it out!!",
        img: require("@/assets/images/web-project-2.jpg"),
      },
      {
        id: 5,
        langProjectName: "MongoDB",
        projectContent: "A Doc oriented Database Maybe you can try it out!!",
        img: require("@/assets/images/web-project-1.jpg"),
      },
    ]);

    return { projectData };
  },
  /* asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
         
        });
      }, 500);
    });
  }, */
  components: {},
  mounted() {
    alert("Hover around & click the card to view more about the project");
  },
};
</script>

<style></style>
