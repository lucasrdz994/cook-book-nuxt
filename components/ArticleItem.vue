<template>
  <article class="box p-0">
    <b-image :src="article.cover" :alt="article.title" ratio="3by1"></b-image>
    <div class="content p-4 is-clearfix">
      <h3>{{ article.title }}</h3>
      <p>{{ article.description }}</p>
      <b-button
        type="is-primary is-light is-pulled-right"
        :to="`/blog/${article.slug}`"
        tag="nuxt-link"
      >
        Ver artículo
      </b-button>
    </div>
  </article>
</template>

<script>
export default {
  props: ['article']
};
</script>

<style>
</style>