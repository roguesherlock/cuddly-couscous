<template>
  <div id="app" class="antialiased text-gray-900">
    <div class="bg-gray-100 min-h-screen flex flex-col">
      <Navbar />
      <Info />
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Info from "./components/Info";
export default {
  name: "app",
  components: {
    Navbar,
    Info,
  },
};
</script>

<style src="./assets/styles/tailwind.css"></style>
