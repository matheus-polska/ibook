<template>
  <div class="book-details">
    <div class="book-cover">
      <img :src="$singleBook.cover" alt="" />
      <NuxtLink class="btn-read-book" to="/1/read">Ler livro</NuxtLink>
    </div>
    <div class="book-info">
      <h2 class="book-title">{{ $singleBook.title }}</h2>
      <div v-html="$singleBook.description" class="book-description"></div>
      <div class="book-categories">
        <div class="categories-list">
          <Chip
            v-for="category in $singleBook.categories"
            :text="category.name"
            :key="category.id"
          />
        </div>
      </div>
      <div class="book-release-details">
        <ul>
          <li>
            <p>Lançamento</p>
            <p>{{ $singleBook.releaseDate }}</p>
          </li>
          <li>
            <p>Autor</p>
            <p>{{ $singleBook.author }}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { books } from '~/store'

export default Vue.extend({
  head() {
    return {
      title: 'Book title',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Book description'
        }
      ]
    }
  },
  computed: {
    $singleBook() {
      return books.$singleBook
    }
  }
})
</script>

<style lang="scss" scoped>
.book-details {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-gap: 1.4rem;
  @include screen('small') {
    grid-template-columns: 1fr;
  }
  @include screen('medium') {
    grid-template-columns: 1fr;
  }

  .book-cover {
    img {
      width: 100%;
    }
    .btn-read-book {
      background: #292929;
      color: #f7f7f7;
      text-transform: uppercase;
      font-weight: 700;
      width: 100%;
      height: 42px;
      font-size: 1.1rem;
      display: grid;
      justify-content: center;
      align-items: center;
      transition: all 300ms ease;
      &:hover {
        opacity: 0.89;
      }
    }
  }
  .book-info {
    .book-title {
      margin-bottom: 2rem;
    }

    .book-description {
      line-height: 1.625rem;
    }

    .book-categories {
      margin-top: 2rem;
    }

    .book-release-details {
      margin-top: 1rem;
      ul {
        display: grid;
        grid-gap: 0.65rem;
        li {
          display: grid;
          grid-template-columns: 160px 1fr;
          font-weight: 700;
          font-size: 13px;
        }
      }
    }
  }
}
</style>
