<template>
  <div class="first-page-container relative z-10 text-white">
    <Header @login="toggleAuthForm" />

    <div class="main-content flex items-center justify-between px-10 py-16 h-screen">
      <!-- Основний контент сторінки -->
      <div class="text-content max-w-lg">
        <h1 class="text-4xl font-bold mb-4">Discover and Find Your Own Fashion!</h1>
        <p class="mb-6 text-gray-300">
          Check out the unique and limited edition digital artwork available as NFTs on our
          platform.
        </p>
        <button
          @click="goToShop"
          class="relative inline-flex items-center justify-center bg-white text-purple-800 font-semibold px-6 py-2 rounded overflow-hidden group"
        >
          <span
            class="absolute inset-0 w-full h-full transition-all duration-300 bg-purple-800 transform scale-x-0 group-hover:scale-x-100"
          ></span>
          <span
            class="relative text-purple-800 transition-colors duration-300 group-hover:text-white"
            >Explore Now</span
          >
          <span
            class="absolute right-2 transition-transform duration-300 transform group-hover:translate-x-2"
          >
            <svg
              class="w-4 h-4 text-white"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M13 7l5 5m0 0l-5 5m5-5H6"
              ></path>
            </svg>
          </span>
        </button>
      </div>

      <div class="character-image bg-purple-600 rounded-lg p-4">
        <img src="@/assets/skelet.png" alt="Character" class="w-48 h-48 object-cover rounded" />
      </div>
    </div>

    <AuthForm v-if="showAuthForm" />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import AuthForm from '@/components/AuthForm.vue'
import { useRouter } from 'vue-router' // Імпортуємо useRouter

export default {
  name: 'FirstPage',
  components: {
    Header,
    AuthForm,
  },
  data() {
    return {
      showAuthForm: false,
    }
  },
  methods: {
    toggleAuthForm() {
      this.showAuthForm = !this.showAuthForm
    },
    goToShop() {
      // Використовуємо $router для переходу на сторінку Shop
      this.$router.push({ name: 'Shop' })
    },
  },
}
</script>
