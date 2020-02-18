<template>
  <div class="card is-mx-auto is-my-5">
    <header class="card-header is-size-4 is-py-2 is-px-3">
      {{ title }}
    </header>
    <div class="card-image">
      <figure class="image">
        <img :src="imageSrc">
      </figure>
    </div>
    <div class="content is-p-3 is-mb-0">
      <p class="has-text-justified">
        {{ content }}
      </p>
    </div>
    <footer class="card-footer">
      <a v-for="(link, i) in links" :key="i" :href="link.url" class="card-footer-item" target="_blank">{{ link.name }}</a>
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
    imageSrc: {
      type: String,
      default: ''
    },
    links: {
      type: Array,
      default () {
        return []
      }
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
