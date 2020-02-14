<template>
  <div id="social-media-icons">
    <ul class="title">
      <li v-for="(item, index) in snsItems" :key="index" class="is-inline">
        <a :href="item.url">
          <b-icon :icon="item.icon.name" :pack="item.icon.pack" size="is-large" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    snsItems: {
      type: Array,
      default: () => []
    }
  }
}
</script>
