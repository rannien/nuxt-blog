<template>
  <div>
    <input
      v-model="searchQuery"
      type="search"
      autocomplete="off"
      placeholder="Search Articles"
      class="form-input px-4 py-3 rounded-xl border-green-300 border-2"
    />
    <ul v-if="articles.length">
      <li v-for="article of articles" :key="article.slug">
        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          {{ article.title }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        searchQuery: '',
        articles: []
      }
    },
    watch: {
      async searchQuery(searchQuery) {
        if (!searchQuery) {
          this.articles = []
          return
        }
        this.articles = await this.$content('articles')
          .limit(6)
          .search(searchQuery)
          .fetch()
      }
    }
  }
</script>
