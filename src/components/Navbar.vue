<template>
  <header class="border-t-4 border-teal-500 ">
    <div class="max-w-6xl mx-auto flex justify-between">
      <nav class="ml-6 flex items-center px-4 py-3 sm:p-0 text-teal-500 ">
        <svg
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M15 19l-7-7 7-7"
          ></path>
        </svg>
        <a class="uppercase leading-loose" href="#">Go Back</a>
      </nav>
      <div
        @click="isOpen = !isOpen"
        class="box-content cursor-pointer select-none mr-6"
      >
        <div
          class="bg-gray-900 realative rounded-b flex items-center justify-around"
        >
          <p class="text-white font-semibold py-3 px-4 text-lg">username</p>
          <div
            class="mr-2 rounded-full bg-teal-300 text-gray-900 h-8 w-8 flex items-center justify-center"
          >
            AS
          </div>
        </div>
        <div
          v-if="isOpen"
          class="absolute mt-2 bg-gray-300 rounded shadow transition-opacity mx-auto max-w-sm"
        >
          <a href="#" class="block px-4 py-2 rounded hover:bg-teal-300"
            >Account</a
          >
          <a href="#" class="block px-4 py-2 rounded hover:bg-teal-300"
            >Settings</a
          >
          <a href="#" class="block px-4 py-2 rounded hover:bg-teal-300"
            >Log out</a
          >
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      isOpen: false,
    };
  },
};
</script>
