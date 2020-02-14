<template>
  <div class="container">
    <section class="section">
      <p v-for="(prj, i) in projects" :key="i">
        <card :title="prj.title" :content="prj.content" :imagePath="prj.imagePath" />
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
        { title: 'test-title', content: 'test-content', imagePath: 'https://www.google.co.jp/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png' }
      ]
    }
  }
}

</script>

<style lang="scss" scoped>
</style>
