<template>
  <main class="relative z-20 flex justify-center items-center md:flex-row flex-col">
    <div
      v-if="sent"
      class="flex rounded-lg border-l-2 border-blue-800 justify-center items-center h-20 max-w-lg inset-x-0 sm:fixed mx-auto relative z-30 bg-yellow-300 top-1/2 bottom-1/2"
    >
      <h2 class="flex justify-center items-center p-1 mx-auto">
        {{ name }} Thank you. message was sent successfully!!
      </h2>
      <div class="flex justify-end items-end">
        <button
          @click="cancel"
          class="flex justify-center items-center h-10 w-10 bg-black text-white p-1 rounded-full"
        >
          X
        </button>
      </div>
    </div>
    <h1
      class="m-5 md:m-3 flex justify-start dark:bg-yellow-400 bg-yellow-100 dark:text-black h-32 w-32 rounded-full items-center border-b-2 border-red-700 mx-20 space-x-12 relative z-20 p-2 inset-x-0 text-black font-extrabold tracking-wider leading-5 uppercase ease-in-out transition-all duration-700 transform shadow-md scale-125 cursor-pointer sm:animate-spin"
    >
      Contact Me
    </h1>

    <form
      @submit.prevent="sendEmail"
      ref="form"
      class="flex justify-center items-center p-2 sm:p-5 sm:dark:bg-ternary-dark sm:bg-primary-light flex-col rounded-lg max-w-0 sm:max-w-5xl sm:w-4/5 mt-2 gap-y-9 sm:border-red-600"
    >
      <input
        required
        type="text"
        v-model="name"
        placeholder="Enter Username.."
        class="font-extrabold text-black py-2 font-mono px-3 outline-black dark:outline-none focus:ring-4 focus:ring-blue-600 rounded-lg sm:w-3/4"
      />
      <input
        type="Email"
        v-model="email"
        required="required"
        placeholder="Enter Email..."
        class="text-black font-extrabold font-mono py-2 px-3 outline-black dark:outline-none focus:ring-4 focus:ring-blue-600 rounded-lg sm:w-3/4"
      />
      <textarea
        required
        name="message"
        v-model="message"
        cols="30"
        rows="10"
        class="text-black py-2 font-bold font-mono px-3 outline-black dark:outline-none focus:ring-4 focus:ring-blue-600 rounded-lg w-60 sm:w-3/4"
        placeholder="Enter your message here..."
      ></textarea>
      <input
        type="submit"
        value="Submit"
        class="md:px-40 px-24 py-2 sm:py-3 outline-none focus:ring-green-600 bg-gradient-to-r from-green-400 to-blue-500 hover:from-pink-500 hover:to-yellow-500 text-white rounded-md"
      />
    </form>
  </main>
</template>

<script>
import emailjs from "@emailjs/browser";

export default {
  data() {
    return {
      name: "",
      email: "",
      message: "",
      sent: false,
    };
  },
  methods: {
    sendEmail(e) {
      try {
        emailjs.sendForm(
          "Francis-Mwaniki",
          "template_wpqslx9",
          e.target,
          this.$refs.form,
          "Oakuddk7bdo-Yt634",
          {
            name: this.name,
            email: this.email,
            message: this.message,
          }
        );
        this.sent = true;
      } catch (error) {
        console.log({ error });
      }
      // Reset form field
      this.name = "";
      this.email = "";
      this.message = "";
    },
    cancel() {
      this.sent = false;
    },
  },
  /*   methods: {
    sendEmail() {
      emailjs
        .sendForm(
          "Francis-Mwaniki",
          "template_wpqslx9",
          this.$refs.form,
          "Oakuddk7bdo-Yt634"
        )
        .then(
          (result) => {
            console.log("SUCCESS!", result.text);
          },
          (error) => {
            console.log("FAILED...", error.text);
          }
        );
    },
  }, */
};
</script>

<style></style>
