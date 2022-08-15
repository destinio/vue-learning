<script lang="ts" setup>
import { reactive, computed } from 'vue'

const { name, books } = reactive({
  name: 'Joe Smith',
  books: ['The Waste Lands', 'The Way of Kings', 'A Storm of Swords'],
})

const hasPublishBooks = computed(() => {
  return books.length > 0 ? 'YES' : 'NO'
})

const bookCounts = computed(() => {
  return books.length
})
</script>
<template>
  <h1>{{ name }}</h1>
  <div>Has books: {{ hasPublishBooks }}</div>
  <div>{{ bookCounts }} books to tell ya the truth</div>
</template>
<style lang="scss" scoped></style>
