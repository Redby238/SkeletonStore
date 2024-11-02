<template>
  <div id="app">
    <FirstPage />
    <GifBackground/>
  </div>
</template>

<script>
import FirstPage from "@/components/FirstPage.vue";
import GifBackground from "./components/GifBackground.vue";

export default {
  name: "App",
  components: {
    FirstPage,
    GifBackground,
  },
};
</script>

<style>

</style>
