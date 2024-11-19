<template>
  <div
    class="features-container p-10 bg-gray-900 bg-opacity-90 rounded-lg mt-20 text-white text-center w-11/12 max-w-7xl mx-auto"
  >
    <h1 class="text-4xl font-extrabold mb-8 text-purple-500">Наша коллекция одежды</h1>
    <p class="text-lg text-gray-300 leading-relaxed text-justify mb-8">
      Ознакомьтесь с нашей уникальной коллекцией стильной и модной одежды. Будь то повседневные
      наряды или особые костюмы, у нас вы найдете все, чтобы создать идеальный образ. Обновите свой
      гардероб с нашей эксклюзивной одеждой!
    </p>

    <div class="clothing-image mb-10 flex justify-center">
      <img
        v-if="featuredProduct.image"
        :src="featuredProduct.image"
        alt="Clothing Image"
        class="w-72 h-72 object-cover rounded-lg shadow-xl"
      />
    </div>

    <h2 class="text-2xl font-semibold text-purple-700 mb-4">Почему выбирают нашу одежду?</h2>
    <ul class="list-disc list-inside text-lg text-gray-300 space-y-4 mb-8 text-left">
      <li>
        <strong>Качественные материалы:</strong> Наша одежда изготовлена из лучших тканей,
        обеспечивая комфорт и долговечность.
      </li>
      <li>
        <strong>Модные дизайны:</strong> Мы следим за последними трендами, чтобы вы всегда были в
        моде.
      </li>
      <li>
        <strong>Доступные цены:</strong> Мы предлагаем стильную одежду по приемлемым ценам, не
        жертвуя качеством.
      </li>
      <li>
        <strong>Эксклюзивные предложения:</strong> Поддержите дизайнеров и получите доступ к
        ограниченным коллекциям.
      </li>
    </ul>

    <h2 class="text-2xl font-semibold text-purple-700 mb-4">Как сделать покупку?</h2>
    <p class="text-lg text-gray-300 leading-relaxed text-justify mb-8">
      Покупка у нас проста и удобна! Просто выберите понравившийся товар и оформите заказ. Мы
      предлагаем быструю доставку и простую систему возвратов.
    </p>

    <h2 class="text-2xl font-semibold text-purple-700 mb-4">
      Присоединяйтесь к нашему миру моды
    </h2>
    <p class="text-lg text-gray-300 leading-relaxed text-justify">
      Станьте частью нашей модной семьи и следите за новыми поступлениями. Мы гарантируем, что у нас
      есть одежда для всех, независимо от вашего стиля и предпочтений.
    </p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Features',
  data() {
    return {
      featuredProduct: {
        image: '',
      },
    };
  },
  methods: {
    async fetchFeaturedProduct() {
      try {
        const { data } = await axios.get('https://api.escuelajs.co/api/v1/products');

        const clothingProducts = data.filter(product => {
          const categories = ['clothes', 'apparel', 'fashion'];
          return categories.some(category => product.title.toLowerCase().includes(category));
        });

        if (clothingProducts.length > 0) {
         
          this.featuredProduct = {
            image: clothingProducts[0].images[0] || '',
          };
        }
      } catch (err) {
        console.error('Ошибка загрузки продукта:', err);
      }
    },
  },
  async created() {
    await this.fetchFeaturedProduct();
  },
};
</script>

<style scoped>
.features-container {
  background-color: rgba(28, 28, 28, 0.9);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
  border-radius: 10px;
  width: 95%;
  max-width: 1500px;
  margin: 80px auto;
}

.features-container h1,
.features-container h2 {
  font-family: 'Inter', sans-serif;
}

.features-container p {
  font-family: 'Roboto', sans-serif;
}
</style>
