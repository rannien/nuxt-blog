<template>
  <div>
    <div class="text-center">
      <h1
        class="text-4xl tracking-tight font-bold text-gray-900 sm:text-5xl mb-4"
      >
        From the blog
      </h1>

      <p class="text-2xl text-gray-500">
        Here you can find the latest articles.
      </p>
    </div>

    <AppSearchInput class="text-center my-4" />

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-4">
      <NuxtLink
        v-for="article of articles"
        :key="article.slug"
        class="w-full rounded-xl shadow-lg"
        :to="{ name: 'blog-slug', params: { slug: article.slug } }"
      >
        <img :src="article.img" class="w-full rounded-t-xl" />
        <div class="p-4">
          <h2 class="text-lg font-semibold text-green-600 mb-2">{{ article.title }}</h2>
          <p class="text-gray-600">{{ article.description }}</p>
        
          <div class="pt-6 flex items-start">
            <figure class="md:flex rounded-xl p-8 md:p-0">
              <img
                class=" w-16 h-16 rounded-full mx-auto"
                :src="article.author.image"
                alt=""
              />
            </figure>

            <figcaption class="font-medium pl-4">
              <div class=" font-semibold">{{ article.author.name }}</div>
              <div class="text-cyan-700">{{ article.updatedAt }}</div>
            </figcaption>
          </div>
          
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const articles = await $content('articles')
      .only(['title', 'description', 'img', 'slug', 'author', 'updatedAt'])
      .sortBy('createdAt', 'asc')
      .fetch()

    return {
      articles,
    }
  },
}
</script>
