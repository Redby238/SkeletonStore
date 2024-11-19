<template>
  <div class="gif-background"></div>
</template>

<script>
export default {
  name: "GifBackground",
};
</script>

<style scoped>
.gif-background {
  width: 100vw;
  height: 100vh;
  background-image: url('@/assets/disco.gif');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1; /* Чтобы фон был позади остального содержимого */
}
</style>
