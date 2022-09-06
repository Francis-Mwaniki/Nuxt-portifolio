<template>
  <main class="dark:bg-ternary-dark bg-ternary-light pb-5 inset-x-0 sm:top-36 relative">
    <Loading />
    <section
      class="pt-16 flex justify-center items-center sm:w-full max-h-full sm:max-w-full max-w-5xl sm:gap-1 flex-col top-4 mx-auto gap-2 p-3"
    >
      <div
        class="flex sm:flex-row sm:justify-between justify-center sm:items-center items-center gap-x-3 flex-col"
      >
        <div class="flex flex-col items-center justify-center gap-y-1 sm:pl-8 min-w-max">
          <!-- <img src="@/assets/pics/infinity.gif" class="h-11 w-11" alt="" /> -->
          <div
            class="font-mono font-extrabold p-2 flex justify-center items-center flex-row"
          >
            <img src="@/assets/images/bookmark.png" class="w-10 h-10" alt="" />
            <span
              class="tabular-nums mt-2 font-mono font-extrabold uppercase text-black dark:text-white text-xl"
            >
              {{ data.title }}</span
            >
          </div>
          <h1 class=""></h1>
          <div
            class="font-mono font-extrabold p-2 flex justify-center items-center flex-row"
          >
            <img
              src="@/assets/images/star.gif"
              class="w-10 h-10 rounded-full p-1"
              alt=""
            />
            <span class="tabular-nums text-lg mt-2 dark:text-white text-black">{{
              data.rating
            }}</span>
          </div>
          <div class="font-mono font-extrabold p-2 dark:text-white text-black">
            {{ data.date }}
          </div>
          <h2
            class="flex justify-center items-center font-mono font-extrabold text-black dark:text-white uppercase tracking-wide underline pb-1 leading-5"
          >
            Technologies Used
          </h2>
          <div
            class="font-mono flex-row p-1 font-extrabold flex justify-start items-center text-black dark:text-white"
            v-for="techStack in data.stack"
          >
            <button
              class="dark:bg-blue-600 bg-yellow-100 border cursor-text border-black hover:bg-white dark:hover:bg-yellow-300 hover:ring-4 p-1 rounded-full"
            ></button>
            <button
              class="m-1 dark:bg-green-500 bg-green-300 border border-gray-400 hover:bg-green-400 dark:hover:bg-green-500 hover:ring-4 p-1 rounded-full"
            >
              {{ techStack }}
            </button>
          </div>
          <div class="flex justify-center items-center flex-row">
            <img
              src="@/assets/images/teal-sourcecode.gif"
              alt=""
              class="w-10 h-10 rounded-full"
            />
            <a :href="data.href" class="flex justify-between items-baseline">
              <h5
                class="font-mono italic hover:underline font-light dark:text-white text-black"
              >
                source code
              </h5>
            </a>
            <img src="@/assets/images/right-arrow.png" class="w-9 h-9" alt="" />
          </div>
        </div>
        <div>
          <img
            :src="data.img"
            :alt="data.title"
            class="rounded-xl cursor-pointer h-3/5 w-3/5 mx-auto"
          />
        </div>
        <div class="flex justify-center items-center flex-col max-w-md sm:p-2 p-3">
          <h2
            class="text-black dark:text-white flex justify-center items-center font-mono font-extrabold uppercase tracking-wide underline pb-1 leading-5"
          >
            About the Project
          </h2>
          <p
            class="rounded-md p-5 italic font-light font-mono dark:text-ternary-light text-black tracking-wide h-52 scrollbar-thumb-rounded-lg scrollbar dark:bg-black bg-ternary-light dark:scrollbar-thumb-yellow-700 scrollbar-thumb-red-700 scrollbar-track-blue-300 overflow-y-scroll hover:scrollbar-thumb-pink-700"
          >
            hello there
          </p>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  asyncData(context) {
    return {
      data: [
        {
          id: 0,
          title: "MongoDB ",
          description:
            "With a document data model that maps to how developers think and code and a powerful, unified query API, MongoDB powers faster, more flexible application development.",
          rating: "5.0",
          date: "july/3rd/2022",
          img: require("@/assets/images/mongodb.jpg"),
          stack: ["NodeJs", "MongoDb", "Express"],
          href: "https://github.com/Francis-Mwaniki/Mongo_Nodejs",
        },
        {
          id: 1,
          title: "Nuxt Js",
          description:
            "Build your next Vue.js application with confidence using Nuxt. An open source framework making web development simple and powerful. Nuxt offers a compelling solution and a great ecosystem to help you ship fullstack Vue apps that are performant and SEO friendly. The flexibility to choose between SSR and SSG is icing on the cake.",
          rating: "5.0",
          date: "june/3rd/2022",
          img: require("@/assets/images/nuxt.jpg"),
          stack: ["NuxtJs", "Express", "Composition Api"],
          href: "https://github.com/Francis-Mwaniki/Nuxt-portifolio",
        },
        {
          id: 2,
          title: "Vue Js",
          description:
            "Approachable==> Builds on top of standard HTML, CSS and JavaScript with intuitive API and world-class documentation. Versatile ==> A rich, incrementally adoptable ecosystem that scales between a library and a full-featured framework.",
          rating: "4.5",
          date: "April/3rd/2022",
          img: require("@/assets/images/vuejs.jpg"),
          stack: ["VueJs", "MongoDb", "Express", "NodeJs"],
          href: "https://github.com/Francis-Mwaniki/My--vue-portifolio",
        },
        {
          id: 3,
          title: "Node Js",
          description: "The no One Js runtime used for making servers Apps",
          rating: "5.0",
          date: "february/3rd/2022",
          img: require("@/assets/images/nodejs.png"),
          stack: ["MongoDb", "Express", "Rest Api"],
          href: "https://github.com/Francis-Mwaniki/mongo_db_node_api",
        },
        {
          id: 4,
          title: "Vue Project",
          description: "The vueJs project for simple questions and answer",
          rating: "5.0",
          date: "may/2nd/2022",
          img: require("@/assets/images/vuejs.jpg"),
          stack: ["VueJs", "Express", "Option Api"],
          href: "https://github.com/Francis-Mwaniki/Mongo_Nodejs",
        },
        {
          id: 5,
          title: "Online Shop",
          description:
            "The no vueJs project used made for Ecommerce. ==>Online shopping is a form of electronic commerce which allows consumers to directly buy goods or services from a seller over the Internet using a web browser or a mobile app. Consumers find a product of interest by visiting the website of the retailer directly or by searching among alternative",
          rating: "5.0",
          date: "July/3rd/2022",
          img: require("@/assets/images/web-project-2.jpg"),
          stack: ["NuxtJs", "MongoDb", "Express", "Composition Api"],
          href: "https://github.com/Francis-Mwaniki/online-shop",
        },
      ].find((el) => el.id == context.params.id),
    };
  },
};
</script>

<style></style>
