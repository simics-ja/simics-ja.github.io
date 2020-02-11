<template>
  <div class="container">
    <section class="has-text-centered section">
      <p v-for="(prj, i) in projects" :key="i">
        <card :title="prj.title" :content="prj.content" :image="prj.image" />
      </p>
    </section>
  </div>
</template>

<script>
import card from '~/components/Card'

export default {
  components: {
    card
  },
  data () {
    return {
      projects: [
        { title: 'test-title', content: 'test-content', image: 'https://www.google.co.jp/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png' }
      ]
    }
  }
}

</script>

<style lang="scss">
</style>
