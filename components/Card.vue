<template>
  <div class="card is-mx-auto is-my-5">
    <header class="card-header is-size-4 is-py-2 is-px-3 has-text-centered">
      {{ title }}
    </header>
    <div class="card-image">
      <figure class="image">
        <img :src="imagePath">
      </figure>
    </div>
    <div class="content is-p-3 is-mb-0">
      <p>
        {{ content }}
      </p>
    </div>
    <footer class="card-footer">
      <a :href="demoUrl" class="card-footer-item" target="_blank">Demo</a>
      <a :href="repoUrl" class="card-footer-item" target="_blank">Repository</a>
    </footer>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Title'
    },
    content: {
      type: String,
      default: ''
    },
    imagePath: {
      type: String,
      default: ''
    },
    demoUrl: {
      type: String,
      default: ''
    },
    repoUrl: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
@import "assets/styles/bulma-override";

* {
  color: $main;
}

.card {
  max-width: 600px;
  border-radius: 6px;
}

</style>
