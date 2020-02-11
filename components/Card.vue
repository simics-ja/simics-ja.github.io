<template>
  <div class="card">
    <div class="card-image">
      <figure class="image">
        <img :src="image">
      </figure>
    </div>
    <div class="media-content">
      <p class="title">
        {{ title }}
      </p>
    </div>
    <div class="content">
      {{ content }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    content: String,
    image: String
  }
}
</script>

<style lang="scss" scoped>

</style>
