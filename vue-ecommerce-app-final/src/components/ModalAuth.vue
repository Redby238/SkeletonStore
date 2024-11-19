<template>
    <div v-if="isVisible" class="modal">
      <div class="modal-content">
        <h1>{{ title }}</h1>
        <p>{{ message }}</p>
        <button @click="closeModal">Close</button>
      </div>
    </div>
  </template>
  
  <script>
export default {
  props: {
    isVisible: {
      type: Boolean,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    message: {
      type: String,
      required: true
    }
  },
  methods: {
    closeModal() {
      this.$emit('update:isVisible', false); // Закриття модального вікна
    }
  }
};
</script>

  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .modal-content {
    background: white;
    padding: 20px;
    border-radius: 10px;
    text-align: center;
  }
  button {
    padding: 10px 20px;
    background-color: #1570f0;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  button:hover {
    background-color: #0056b3;
  }
  </style>
  