<template>
  <main class="scroll-smooth">
    <Loading />
    <Home />
  </main>
</template>

<script lang="ts">
import Vue from "vue";
import Loading from "~/components/Loading.vue";

export default Vue.extend({
  name: "IndexPage",
  components: { Loading },
});
</script>
