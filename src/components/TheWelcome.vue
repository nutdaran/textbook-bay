<script setup>
//import { ref } from 'vue'

defineProps({
  book: {
    type: Object,
    required: true,
  }
})

// const book = ref({
//   isbn: 1001,
//   title: 'CSS for fun',
//   condition: 'Like New',
//   published: 'Feb 2, 2020',
//   price: 400,
//   freeShipping: true,
// })
</script>

<template>
  <div class="product-card">
    <h2>{{ book.title }}</h2>
    <span>Price: {{ book.price }} B , Condition: {{ book.condition }}</span>
  </div>
</template>

<style scoped>
.product-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.product-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>