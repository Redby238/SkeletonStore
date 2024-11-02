<template>
  <div class="gif-background">
    <header class="overlay-header">
      <div class="logo">
        <img src="@/assets/logo.gif" alt="Logo" />
      </div>
      <div class="nav-container">
        <nav class="nav-menu">
          <a v-bind:href="FirstPage">Home</a>
          <a v-bind:href="Shop">Shop</a>
          <a v-bind:href="AboutUs">Features</a>
          <a v-bind:href="Cart">Cart</a>
        </nav>
      </div>
    </header>
  </div>
</template>

<script>
import FirstPage from "@/components/FirstPage.vue";
import Shop from "@/components/Shop.vue";
import AboutUs from "@/components/AboutUs.vue";
import Cart from "@/components/Cart.vue";

export default {
  name: "GifBackground",
  computed: {
    Cart() {
      return Cart;
    },
    AboutUs() {
      return AboutUs;
    },
    Shop() {
      return Shop;
    },
    FirstPage() {
      return FirstPage;
    },
  },
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
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.overlay-header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  z-index: 10;
  padding: 15px;
  display: flex;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
}

.logo img {
  width: 50px;
  height: auto;
}

.nav-container {
  flex-grow: 1;
  display: flex;
  justify-content: center;
}

.nav-menu {
  display: flex;
  gap: 20px;
}

.nav-menu a {
  color: white;
  text-decoration: none;
  font-size: 1.2rem;
  font-weight: 500;
  opacity: 0.8;
  transition: opacity 0.3s;
}

.nav-menu a:hover {
  opacity: 1;
}
</style>