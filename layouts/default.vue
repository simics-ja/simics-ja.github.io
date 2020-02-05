<template>
  <div>
    <section>
      <div class="container has-text-centered">
        <h1 class="title">
          Title
        </h1>
      </div>
    </section>
    <section class="section">
      <nuxt />
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>

<style lang="scss">
// Import Bulma's core
@import "~bulma/sass/utilities/_all";

// Override Bulma's variables
@import "assets/styles/bulma-override";

// Import Bulma and Buefy styles
@import "~bulma";
@import "~buefy/src/scss/buefy";

</style>
