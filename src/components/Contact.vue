<script>
export default {
  name: "TheContact",
  data() {
    return {
      formData: {
        name: "",
        email: "",
        message: ""
      },
      successMessage: ""
    };
  },
  methods: {
    async handleSubmit() {
      try {
        const response = await fetch("https://formspree.io/f/mjkvggdj", {
          method: "POST",
          headers: {
            "Content-Type": "application/json"
          },
          body: JSON.stringify(this.formData)
        });
        if (response.ok) {
        this.successMessage = "Submitted successfully!";
        this.formData = { name: "", email: "", message: "" };
        setTimeout(() => {
          this.successMessage = ""; 
        }, 1000);
      }  else {
          this.successMessage = "There was an error. Please try again.";
        }
      } catch (error) {
        this.successMessage = "There was an error. Please try again.";
      }
    }
  }
};
</script>

<template>
  <div class="flex justify-center my-5 h-full sm:h-[70vh] items-center bg-[#232325]" id="contact">
    <div class="max-w-[350px] md:max-w-[1200px] mx-auto my-10">
      <div class="grid grid-cols-1 md:grid-cols-2">
        <div class="p-6 bg-gray-800 rounded-xl flex flex-col justify-around">
          <h1 class="text-4xl sm:text-5xl text-white">
            Contact <span>Me</span>
          </h1>
          <p class="text-lg text-gray-400 mt-2">
            Let's connect on LinkedIn <br />or send me an Email
          </p>
          <div class="flex items-center mt-2 text-gray-400">
            <div class="text-2xl">
              <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 32 32" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg">
                <path d="M 3 8 L 3 26 L 29 26 L 29 8 Z M 7.3125 10 L 24.6875 10 L 16 15.78125 Z M 5 10.875 L 15.4375 17.84375 L 16 18.1875 L 16.5625 17.84375 L 27 10.875 L 27 24 L 5 24 Z"></path>
              </svg>
            </div>
            <div class="ml-4 text-md tracking-wide font-semibold w-40">
              <p>Kaltrinë Baliu</p>
            </div>
          </div>
        </div>

        <form class="md:p-3 flex flex-col justify-center" @submit.prevent="handleSubmit">
          <div class="flex flex-col">
            <input
              type="text"
              name="name"
              placeholder="Full Name"
              v-model="formData.name"
              class="w-100 mt-2 p-3 rounded-lg bg-gray-800 border-gray-700 text-white focus:border-blue-800 focus:ring-blue-900"
              required
            />
          </div>
          <div class="flex flex-col">
            <input
              type="email"
              name="email"
              placeholder="Email"
              v-model="formData.email"
              class="w-100 mt-2 p-3 rounded-lg bg-gray-800 border-gray-700 text-white focus:border-blue-800 focus:ring-blue-900"
              required
            />
          </div>
          <div class="flex flex-col">
            <textarea
              name="message"
              placeholder="Your Message"
              v-model="formData.message"
              class="w-100 mt-2 p-3 rounded-lg bg-gray-800 border-gray-700 text-white focus:border-blue-800 focus:ring-blue-900"
              required
            ></textarea>
          </div>

          <button
            type="submit"
            class="bg-purple-700 hover:bg-purple-800 active:bg-purple-900 text-white py-3 rounded-lg mt-3 focus:outline-none focus:ring-2 focus:ring-purple-300"
          >
            Submit
          </button>
          <p v-if="successMessage" class="text-green-500 mt-2">{{ successMessage }}</p>
        </form>
      </div>
    </div>
  </div>
</template>

