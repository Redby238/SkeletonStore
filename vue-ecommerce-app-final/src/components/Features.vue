<template>
  <div
    class="features-container p-10 bg-gray-900 bg-opacity-90 rounded-lg mt-20 text-white text-center w-11/12 max-w-7xl mx-auto"
  >
    <h1 class="text-4xl font-extrabold mb-8 text-purple-500">Наша колекція NFT картинок</h1>
    <p class="text-lg text-gray-300 leading-relaxed text-justify mb-8">
      Ознайомтесь з унікальними та обмеженими цифровими творами мистецтва, доступними як NFT на
      нашій платформі. Кожен витвір є неповторним, ідеальним для колекціонерів, любителів мистецтва.
      Купуйте, продавайте та обмінюйте ці ексклюзивні твори, ставши частиною світу NFT мистецтва.
    </p>

    <div class="nft-image mb-10 flex justify-center">
      <img
        src="@/png/1.png"
        alt="NFT Cat Image"
        class="w-72 h-72 object-cover rounded-lg shadow-xl"
      />
    </div>

    <h2 class="text-2xl font-semibold text-purple-700 mb-4">Чому обирають наші NFT?</h2>
    <ul class="list-disc list-inside text-lg text-gray-300 space-y-4 mb-8 text-left">
      <li>
        <strong>Унікальні твори мистецтва:</strong> Кожна картинка кота унікально створена та
        токенізована на блокчейні.
      </li>
      <li>
        <strong>Обмежена кількість:</strong> Кожен NFT доступний в обмеженій кількості, що
        забезпечує рідкість та ексклюзивність.
      </li>
      <li>
        <strong>Безпечні транзакції:</strong> Усі транзакції надійно фіксуються на блокчейні для
        прозорості та автентичності.
      </li>
      <li>
        <strong>Підтримка художників:</strong> Кожна покупка підтримує талановитих цифрових
        художників, які спеціалізуються на котячих малюнках.
      </li>
    </ul>

    <h2 class="text-2xl font-semibold text-purple-700 mb-4">Як купити NFT?</h2>
    <p class="text-lg text-gray-300 leading-relaxed text-justify mb-8">
      Купити NFT дуже просто! Перегляньте нашу колекцію, оберіть улюблену картину і завершите
      покупку за допомогою криптовалюти. Після покупки NFT буде додано до вашого гаманця, і ви
      станете власником унікального цифрового твору мистецтва, який можна перепродати або виставити
      в віртуальній галереї.
    </p>

    <h2 class="text-2xl font-semibold text-purple-700 mb-4">
      Приєднуйтесь до революції NFT картин
    </h2>
    <p class="text-lg text-gray-300 leading-relaxed text-justify">
      Станьте частиною великої спільноти колекціонерів NFT та любителів котів. Незалежно від того,
      чи шукаєте ви інвестиції, чи просто любите котів, у нашій колекції знайдеться щось для
      кожного!
    </p>
  </div>
</template>

<script>
export default {
  name: 'Features',
}
</script>

<style scoped>
.features-container {
  background-color: rgba(28, 28, 28, 0.9); /* Темний фон з прозорістю */
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5); /* Тінь для глибини */
  border-radius: 10px;
  width: 95%;
  max-width: 1500px;
  margin: 80px auto;
}

.features-container h1,
.features-container h2 {
  font-family: 'Inter', sans-serif; /* Сучасний шрифт */
}

.features-container p {
  font-family: 'Roboto', sans-serif; /* Легкий шрифт для зручності читання */
}
</style>
