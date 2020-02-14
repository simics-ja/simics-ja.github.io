<template>
  <div class="card is-mx-auto">
    <header class="card-header title is-py-2 is-px-3">
      {{ title }}
    </header>
    <div class="card-image">
      <figure class="image">
        <img :src="imagePath">
      </figure>
    </div>
    <div class="content is-p-3">
      <p>
        {{ content }}
      </p>
    </div>
    <footer class="card-footer has">
      <a :href="demoUrl" class="card-footer-item">Demo</a>
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
      default: '#'
    },
    demoUrl: {
      type: String,
      default: '#'
    },
    srcUrl: {
      type: String,
      default: '#'
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
