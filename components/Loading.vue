<template>
  <div class="relative z-30 inset-x-0 top-20 opacity-70 bg-yellow-100 h-full w-full">
    <!--    <p> -->
    <button
      v-if="loading"
      class="flex justify-center items-center mx-auto text-black font-extrabold rounded-lg bg-yellow-100 h-4/5"
    >
      <img src="@/assets/pics/infinity.gif" class="h-11 w-11 rounded-full" alt="" />
      <span class="h-96 flex justify-center items-center">{{
        loading ? "Please wait This will take a second.." : ""
      }}</span>
    </button>
    <!-- loading...
    </p>-->
  </div>
</template>

<script>
export default {
  data: () => ({
    loading: false,
  }),
  methods: {
    start() {
      this.loading = true;
    },
    finish() {
      this.loading = false;
    },
  },
  mounted() {
    this.start();
    setTimeout(() => {
      this.finish();
    }, 5000);
  },
};
</script>

<style scoped></style>
