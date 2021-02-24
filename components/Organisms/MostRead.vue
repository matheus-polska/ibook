<template>
  <div class="most-read">
    <h2>Mais lidos da semana</h2>
    <div class="most-read-books">
      <BookCard
        v-for="book in $allBooks.mostReadOfWeek"
        :book="book"
        :key="book.id"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { books } from '~/store'

export default Vue.extend({
  computed: {
    $allBooks() {
      return books.$allBooks
    }
  }
})
</script>

<style lang="scss" scoped>
.most-read {
  display: grid;
  grid-gap: 1.3rem;
  h2 {
    font-size: 1.375rem;
    font-weight: 500;
    color: $dark;
  }
  .most-read-books {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: auto;
    grid-gap: 2rem;
    @include screen('small') {
      grid-template-columns: repeat(2, 1fr);
    }
    @include screen('medium') {
      grid-template-columns: repeat(3, 1fr);
    }
  }
}
</style>
