<template>
  <div class="container">
    <div class="box p-0">
      <b-image
        :src="article.cover"
        :alt="article.title"
        ratio="3by1"
      ></b-image>
      <div class="content p-4">
        <div class="columns">
          <div class="column is-four-fifths">
            <h1 class="is-size-2 mb-6">{{ article.title }}</h1>
            <nuxt-content :document="article"></nuxt-content>
          </div>
          <div class="column">
            <h3 class="is-size-4">Ingredientes</h3>
            <ul class="m-0">
              <li
                class="ingredientItem"
                v-for="(ingredient, index) in article.ingredients"
                :key="index"
              >
                <b-icon size="is-small" icon="checkbox-marked-circle-outline" class="mr-2"></b-icon>
                {{ ingredient }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('blog', params.slug).fetch();

    return {
      article
    }
  }
}
</script>

<style lang="scss">
  .ingredientItem {
    list-style: none;
  }
</style>