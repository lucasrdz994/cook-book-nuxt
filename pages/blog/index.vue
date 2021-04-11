<template>
  <div>
    <section class="hero is-primary mb-6">
      <div class="hero-body">
        <p class="title">Recetas únicas</p>
        <p class="subtitle">Descubre que vas a cocinar hoy.</p>
      </div>
    </section>
    <div class="container">
      <div class="columns">
        <aside class="column">
          Lista de Tags
        </aside>
        <main class="column is-four-fifths">
          <div class="box p-0">
            <b-image
              src=""
              alt=""
              ratio="3by1"
            ></b-image>
            <div class="content p-4 is-clearfix">
              <h3>Titulo</h3>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ab, omnis voluptas minima quasi consectetur libero minus, laudantium earum aperiam reprehenderit ipsa dolor nihil sunt numquam tempora laborum, vitae officiis! Dolor!</p>
              <b-button
                type="is-primary is-light is-pulled-right"
                to="/blog/empandas-tucumanas"
                tag="nuxt-link"
              >
                Ver artículo
              </b-button>
            </div>
          </div>
        </main>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>