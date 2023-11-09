<script setup>
import { ref, onMounted } from 'vue'
import ProductCard from '@/components/ProductCard.vue'
// import axios from 'axios'
import BookService from '../services/BookService';

const books = ref(null)

onMounted(() => {
  // axios.get('https://my-json-server.typicode.com/nutdaran/webapp-test/books')
  // .then((response)=> {
  //   books.value = response.data //keep data in books
  // })
  // .catch((error) => {
  //   console.log(error)
  // })
    BookService.getBooks()
  .then((response)=> {
    books.value = response.data
  })
  .catch((error) => {
    console.log(error)
  })
})
</script>

<template>
  <div class="products">
    <ProductCard v-for="book in books" :key="book.id" :book="book" /> <!--display-->
  </div>
</template>