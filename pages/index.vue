<template>
  <main>
    <section class="hero is-large is-light">
      <div class="hero-body py-6">
        <div class="container">
          <div class="columns">
            <div class="column is-flex is-flex-direction-column is-justify-content-center is-align-items-start">
              <h1 class="title is-size-2">Descubre que vas a comer {{ nextMeal }}</h1>
              <h2 class="subtitle is-size-4">Tenemos las mejores recetas para toda ocación.</h2>
              <b-button class="has-text-white" type="is-primary" size="is-large" tag="nuxt-link" to="/blog">Todas las recetas</b-button>
            </div>
            <div class="column">
              <b-image
                :src="require('~/assets/svg/hero-home.svg')"
                class="hero-home-svg"
              ></b-image>
            </div>
          </div>
        </div>
      </div>
    </section>
    <Promotion />
  </main>
</template>

<script>
export default {
  name: "HomePage",
  head() {
    return {
      script: [
        { src: "https://identity.netlify.com/v1/netlify-identity-widget.js" },
      ],
    };
  },
  data() {
    return {
      now: new Date().getHours()
    }
  },
  computed: {
    nextMeal() {
      if (this.now < 13) {
        return 'este medio día.';
      }
      if (this.now > 13 && this.now < 19) {
        return 'esta tarde.';
      }
      if (this.now > 19) {
        return 'esta noche.';
      }
    }
  }
};
</script>

<style scoped lang="scss">
  .hero-home-svg {
    width: 60%;
    height: auto;
    margin-left: auto;
  }
</style>