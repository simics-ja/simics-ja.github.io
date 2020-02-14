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
  },
  asyncData () {
    return {
      projects: require('assets/jsons/projects.json').projects
    }
  }
}

</script>

<style lang="scss" scoped>
</style>
