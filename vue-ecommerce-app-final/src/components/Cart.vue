<template>
  <div
    class="cart-container p-10 bg-gray-900 bg-opacity-90 rounded-lg mt-20 text-white text-center w-11/12 max-w-7xl mx-auto"
  >
    <h1 class="text-4xl font-extrabold mb-8">Your Cart</h1>

    <div v-if="cartItems.length === 0" class="empty-cart text-xl font-semibold text-gray-400">
      <p>Ваш кошик порожній.</p>
    </div>

    <div v-else>
      <ul class="cart-items flex flex-wrap justify-center gap-5 mb-10">
        <li
          v-for="(item, index) in cartItems"
          :key="index"
          class="cart-item flex flex-col items-center w-full md:w-1/2 lg:w-1/3 p-5 bg-purple-800 rounded-lg shadow-lg hover:shadow-2xl transform hover:-translate-y-2 transition-all"
        >
          <div class="item-info flex items-center mb-4">
            <img
              :src="item.image"
              alt="product image"
              class="item-image w-16 h-16 object-cover rounded-md mr-4"
            />
            <div class="item-details text-left">
              <p class="item-name text-xl font-semibold">{{ item.name }}</p>
              <p class="item-price text-lg text-gray-300">${{ item.price }}</p>
            </div>
          </div>
          <button
            @click="removeFromCart(index)"
            class="remove-item-btn mt-4 bg-red-600 hover:bg-red-700 text-white px-4 py-2 rounded-md font-bold"
          >
            Видалити
          </button>
        </li>
      </ul>

      <div
        class="cart-summary flex flex-col md:flex-row items-center justify-between p-5 bg-gray-100 rounded-lg text-gray-800"
      >
        <p class="text-2xl font-semibold">Total: ${{ totalAmount }}</p>
        <button
          @click="proceedToCheckout"
          class="checkout-btn mt-4 md:mt-0 bg-green-500 hover:bg-green-600 text-white px-8 py-3 rounded-md font-bold transition-colors"
        >
          Оформити замовлення
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cart',
  data() {
    return {
      cartItems: [], // Масив для кошика
    }
  },
  computed: {
    totalAmount() {
      const total = this.cartItems.reduce((total, item) => total + item.price, 0)
      return total.toFixed(2) // Округлення до 2 знаків після коми
    },
  },
  methods: {
    loadCart() {
      const savedCart = JSON.parse(localStorage.getItem('cart'))
      if (savedCart) {
        this.cartItems = savedCart
      }
    },
    saveCart() {
      localStorage.setItem('cart', JSON.stringify(this.cartItems))
    },
    removeFromCart(index) {
      this.cartItems.splice(index, 1)
      this.saveCart()
    },
    proceedToCheckout() {
      this.$router.push({ name: 'Checkout' })
    },
  },
  created() {
    this.loadCart()
  },
}
</script>

<style scoped>
/* Додаткові стилі для картки товару */
.cart-item {
  transition: transform 0.3s ease;
}

.cart-item:hover {
  transform: translateY(-8px);
}
</style>
