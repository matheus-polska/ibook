<template>
  <HomeTemplate />
</template>

<script lang="ts">
import Vue from 'vue'
import { books } from '~/store'

export default Vue.extend({
  created() {
    books.fetchBooks()
  }
})
</script>

<style></style>
