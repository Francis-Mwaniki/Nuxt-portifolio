<!-- Please remove this file from your project -->
<template>
  <!-- Starter Image -->
  <main class="relative z-20">
    <Loading />
    <!--     <Nav /> -->
    <!-- Background Image -->
    <section class="">
      <img
        src="../assets/pics/heros.jpg"
        alt="pic"
        width="100%"
        class="absolute object-cover -top-10 bottom-0 inset-x-0"
        style="height: 100%"
      />
      <!--  <video
        src="../assets/pics/Lines.mp4"
        class="object-cover absolute inset-x-0"
        autoplay="autoplay"
        muted="muted"
        loop="loop"
        style="top: 0px; height: 100%"
      ></video> -->
    </section>
    <h1
      class="flex justify-start items-center border-b-2 border-red-700 sm:mx-20 mx-auto space-x-3 md:space-x-12 relative z-20 md:p-2 p-1 m-1 inset-x-0 text-white font-extrabold md:tracking-wider md:leading-5 uppercase"
    >
      <span class="">
        <img src="@/assets/images/work.png" class="h-11 w-11" alt=""
      /></span>
    </h1>
    <!-- Display Projects -->
    <div class="flex justify-center items-center">
      <Screenshot />
    </div>
    <div class="flex justify-center items-center">
      <Projects />
    </div>
    <!-- Developer Intro -->
    <h2
      class="flex justify-start pl-5 items-start mx-auto dark:text-primary-light relative z-20 text-yellow-600 uppercase cursor-pointer text-3xl"
    >
      About Me
    </h2>
    <section
      class="flex md:flex-row flex-col flex-wrap justify-center gap-5 items-center pt-2 sm:mt-4 mt-3 relative z-20 dark:text-white text-black sm:h-auto h-5/6 dark:bg-ternary-dark bg-ternary-light mx-auto max-w-full space-x-4 p-2 rounded-md"
    >
      <div
        class="dark:bg-gray-700 bg-gray-200 p-6 sm:max-w-2xl max-w-3xl sm:h-44 h-full rounded-md mx-auto"
      >
        <h2 class="uppercase font-extrabold font-mono border-red-600 mx-auto">
          <span class="p-1"
            >Hello i'm
            <span class="uppercase font-extrabold text-yellow-600">francis</span
            ><span class="border-b-2 border-red-600 mx-auto"> mwaniki</span></span
          >
          <div
            class="px-1 font-mono uppercase text-left dark:text-yellow-400 text-red-600"
          >
            i am a fullstack developer by profession
          </div>
        </h2>
        <!-- Import Social Img -->
        <div class="flex justify-between items-start py-2">
          <SocialMedial />
          <button
            class="rounded-xl px-5 py-0 md:px-6 sm:py-3 sm:mt-2 mt-2 dark:text-white text-black bg-primary-light dark:bg-primary-dark hover:bg-ternary-dark hover:text-primary-light"
          >
            <a
              href="/Francis.pdf"
              download="download"
              class="flex justify-center items-center flex-row p-1"
            >
              <img
                src="@/assets/pics/download.gif"
                class="h-7 w-7 rounded-full"
                alt=""
              /><span class="px-1"> CV</span>
            </a>
          </button>
        </div>
      </div>
      <div class="">
        <img
          src="@/assets/pics/svg/developer-dark.svg"
          width="100%"
          height="100%"
          alt=""
        />
      </div>
    </section>
    <About />
    <Contact />
    <Hobbies />
    <Footer />
  </main>
</template>

<script>
import { ref } from "vue";
import SocialMedial from "./SocialMedial.vue";
import AboutMe from "~/pages/AboutMe.vue";
import About from "./About.vue";
import Contact from "./Contact.vue";
import Hobbies from "./Hobbies.vue";
import Projects from "~/pages/work/Projects.vue";
import Footer from "./Footer.vue";

/* import Nav from "./Nav.vue"; */
export default {
  name: "NuxtTutorial",
  components: {
    SocialMedial,
    AboutMe,
    About,
    Contact,
    Hobbies,
    Projects,
    Footer,
  },
  mounted() {
    alert("Navigate to Projects Navigation Bar to View Projects!!");
  },
};
</script>
