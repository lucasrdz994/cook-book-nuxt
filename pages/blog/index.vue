<template>
  <div>
    <section class="hero mb-6">
      <div class="hero-body">
        <div class="container">
          <p class="title">Recetas únicas</p>
          <p class="subtitle">Descubre que vas a cocinar hoy.</p>
        </div>
      </div>
    </section>
    <div class="container">
      <div class="columns">
        <aside class="column">
          <h3 class="is-size-3 mb-4">Categorías</h3>
          <div class="buttons is-flex is-align-items-flex-start is-flex-direction-column">
            <b-button
              v-for="category in categories"
              :key="category.title"
              type="is-ghost"
              tag="nuxt-link"
              :to="`/blog?category=${category.title}`"
            >
              {{ category.title }}
            </b-button>
          </div>
        </aside>
        <main class="column is-four-fifths">
          <ArticleItem 
            :article="article" 
            v-for="article in articles" 
            :key="article.slug" />
        </main>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, query }) {
    let articles;
    if (query.category) {
      articles = await $content('blog')
      .where({categories: { $containsAny: query.category }})
      .only(['title', 'description', 'slug', 'cover']).fetch();
    } else {
      articles = await $content('blog')
      .only(['title', 'description', 'slug', 'cover']).fetch();
    }

    
    const categories = await $content('category').fetch();

    return {
      articles,
      categories
    }
  },
  watchQuery: ['category']
};
</script>

<style lang="scss">
  .hero {
    background-color: #e6d5b8;
  }
</style>